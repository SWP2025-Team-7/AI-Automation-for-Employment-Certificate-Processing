# Quality Characteristics & Attribute Scenarios

This document describes the key quality attributes of the **AI Automation for Employment Certificate Processing** system and specific scenarios illustrating how the system should behave.

---

## 1. Reliability

**Scenario:** OCR Service Failure

* **Context:** A batch of 5 PDF documents is submitted via the Telegram Bot.
* **Stimulus:** One call to the external OCR API returns a 5xx error.
* **Environment:** Docker containers orchestrated by `docker-compose` (configuration in Core).
* **Artifact:** `backend/ocr_worker.py` module.
* **Response:**

  1. Retry the request up to 3 times.
  2. If still failing, rollback the database transaction and enqueue the task for a retry.
  3. Return a clear error message to the Telegram Bot without interrupting processing of other documents.

---

## 2. Performance

**Scenario:** Single Document Processing

* **Context:** `dev` branch of Backend, `main` branch of Bot, under light load (up to 3 concurrent requests).
* **Stimulus:** A user uploads a two-page PDF certificate via the chat bot.
* **Environment:** Server with 2 vCPU and 4 GB RAM.
* **Artifact:** FastAPI endpoint `POST /documents/upload`.
* **Response:**

  * Total processing time from upload to bot response ≤ 2 seconds.
  * Peak memory usage ≤ 1 GB.

---

## 3. Security

**Scenario:** Unauthorized Access Attempt

* **Context:** Web-Application communicates with Core API.
* **Stimulus:** HTTP client without a valid JWT token requests `GET /api/v1/certificates`.
* **Environment:** HTTPS with CORS restricted to the web application's domain.
* **Artifact:** Authentication middleware in Core.
* **Response:**

  1. Respond with HTTP 401 Unauthorized.
  2. Log the attempt with WARN level without storing sensitive information.

---

## 4. Maintainability

**Scenario:** Adding an Email Notification

* **Context:** Backend.  
* **Stimulus:** We need to send the OCR result by email to the student, in addition to saving it in the log.  
* **Environment:** Plain Python 3.11 environment; CI checks via a basic GitHub Actions workflow.  
* **Artifact:** The module `backend/notifications.py`.  
* **Response:**  
  1. In `backend/notifications.py`, add a new class `EmailNotifier` that uses Python’s `smtplib` to send a simple message (e.g. SMTP via Gmail).  
  2. Do **not** change the existing log-writing code—it must keep working unchanged.  
  3. Run `pytest` and confirm **all** current tests still pass.  
  4. Write at least **two** new unit tests for `EmailNotifier` (e.g. mock SMTP server, check that `send_mail()` is called with correct parameters).
---

## 5. Scalability

**Scenario:** Scaling OCR Services

* **Context:** Core and Web-Application under peak load of 50 requests/min.
* **Stimulus:** Scale Backend service instances to 3 via Docker Compose or Kubernetes HPA.
* **Environment:** RabbitMQ queue handling OCR tasks with auto-scaling consumers.
* **Artifact:** OCR worker containers.
* **Response:**

  1. New instances automatically consume from the queue.
  2. Average processing time per document decreases proportionally with the number of instances.
  3. System remains stable with queue depths up to 500 tasks.
