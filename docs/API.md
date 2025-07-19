# AI Automation for Employment Certificate Processing API Documentation

## Overview

> AI Automation for Employment Certificate Processing is a service that helps students to upload internship references
>and helps university workers to easily monitor information about students.


## How to find

[Link](https://github.com/SWP2025-Team-7/Backend)

---

### users

- Endpoints from `routes/users.py`
- Prefix = `"/users"`

---
<details> 
<summary> POST <b>/users/</b> Users:Create-User </summary>

##### **Description**

Add new user in database

##### **Request body**

```json
{
    {
      "user_id": 0,
      "alias": "string"
    }
}
```

##### **Responses**

---

<details> <summary> <b>Code</b> - 200 </summary>

**Description** - User updated.

**Example Value**:

```json
   {
  "user_id": 0,
  "alias": "string",
  "mail": "string",
  "name": "string",
  "surname": "string",
  "patronymic": "string",
  "phone_number": "string",
  "citizens": "string",
  "duty_to_work": "yes",
  "duty_status": "working",
  "grant_amount": 0,
  "duty_period": 0,
  "company": "string",
  "position": "string",
  "start_date": "2025-07-17",
  "end_date": "2025-07-17",
  "salary": 0
 }
```

</details>

---

<details> <summary> <b>Code</b> - 201 </summary>

**Description** - User created

**Example Value**:

```json
 {
  "user_id": 0,
  "alias": "string",
  "mail": "string",
  "name": "string",
  "surname": "string",
  "patronymic": "string",
  "phone_number": "string",
  "citizens": "string",
  "duty_to_work": "yes",
  "duty_status": "working",
  "grant_amount": 0,
  "duty_period": 0,
  "company": "string",
  "position": "string",
  "start_date": "2025-07-17",
  "end_date": "2025-07-17",
  "salary": 0
 }
```

</details>

---

<details> <summary> <b>Code</b> - 400 </summary>

**Description** - User already exists

**Example value**:

```json
 {
  "user_id": 0,
  "alias": "string",
  "mail": "string",
  "name": "string",
  "surname": "string",
  "patronymic": "string",
  "phone_number": "string",
  "citizens": "string",
  "duty_to_work": "yes",
  "duty_status": "working",
  "grant_amount": 0,
  "duty_period": 0,
  "company": "string",
  "position": "string",
  "start_date": "2025-07-17",
  "end_date": "2025-07-17",
  "salary": 0
 }
```

</details>

---

<details> <summary> <b>Code</b> - 422 </summary>

**Description** - Validation Error

**Example value**:

```json
{
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}
```

---

</details>

</details>

<details>

<summary> GET <b>/users/{user_id}</b> Users:Get-User</summary>

##### **Description**

Searching for the student in database

##### **Parameters**

|name|description|
|---|---|
|user_id|0|

##### **Responses**

###### **Curl**

```bash
 curl -X 'GET' \
  'http://localhost:8000/users/0' \
  -H 'accept: application/json'
```

###### Request URL

`http://localhost:8000/users/0`

###### Server Responses

<details> 

<summary> <b>Code</b> - 200 </summary>

**Description** - User found

**Example value**

```json
{
  "user_id": 0,
  "alias": "string",
  "mail": "string",
  "name": "string",
  "surname": "string",
  "patronymic": "string",
  "phone_number": "string",
  "citizens": "string",
  "duty_to_work": "yes",
  "duty_status": "working",
  "grant_amount": 0,
  "duty_period": 0,
  "company": "string",
  "position": "string",
  "start_date": "2025-07-17",
  "end_date": "2025-07-17",
  "salary": 0
 }
```

</details>

<details> 

<summary> <b>Code</b> - 404 </summary>

**Description** User not found

</details>

<details> 

<summary> <b>Code</b> - 422 </summary>

**Description** Validation Error

**Example Value**

```json
 {
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
 }
```

</details>

</details>

<details>

<summary> PATCH <b>/users/{user_id}</b> Users:Update-User</summary>

##### **Description**

To update information about student.

##### **Parameters**

|name|description|
|---|---|
|user_id|0|

##### **Request body**

```json
 {
  "user_id": 0,
  "alias": "string",
  "mail": "string",
  "name": "string",
  "surname": "string",
  "patronymic": "string",
  "phone_number": "string",
  "citizens": "string",
  "duty_to_work": "yes",
  "duty_status": "working",
  "grant_amount": 0,
  "duty_period": 0,
  "company": "string",
  "position": "string",
  "start_date": "2025-07-14",
  "end_date": "2025-07-04",
  "salary": 0
 }
```

##### **Responses**

###### **Curl**

```bash
  curl -X 'PATCH' \
  'http://localhost:8000/users/0' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "user_id": 0,
  "alias": "string",
  "mail": "string",
  "name": "string",
  "surname": "string",
  "patronymic": "string",
  "phone_number": "string",
  "citizens": "string",
   "duty_to_work": "yes",
  "duty_status": "working",
  "grant_amount": 0,
  "duty_period": 0,
  "company": "string",
  "position": "string",
  "start_date": "2025-07-14",
  "end_date": "2025-07-04",
  "salary": 0
 }'
```

###### Request URL

`http://localhost:8000/users/0`

###### Server Responses

<details>

<summary> <b>Code</b> - 200</summary>

**Description** -  User updated

**Example value**

```json
{
  "user_id": 0,
  "alias": "string",
  "mail": "string",
  "name": "string",
  "surname": "string",
  "patronymic": "string",
  "phone_number": "string",
  "citizens": "string",
  "duty_to_work": "yes",
  "duty_status": "working",
  "grant_amount": 0,
  "duty_period": 0,
  "company": "string",
  "position": "string",
  "start_date": "2025-07-17",
  "end_date": "2025-07-17",
  "salary": 0
 }
```

</details>

<details> 

<summary> <b>Code</b> - 404 </summary>

**Description** User not found

</details>

<details> 

<summary> <b>Code</b> - 422 </summary>

**Description** Validation Error

**Example Value**

```json
 {
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
 }
```

</details>

</details>

<details>

<summary>  DELETE <b>/users/{user_id}</b> Users:Delete-User </summary>

##### **Description**

Deletion user from database

##### **Parameters**

|name|description|
|---|---|
|user_id|0|

##### **Responses**

<details>

<summary> <b>Code</b> - 200 </summary>

**Description** - User deleted

**Example Value** - `"string"`

</details>

<details> 

<summary> <b>Code</b> - 404 </summary>

**Description** User not found

</details>

<details>

<summary> <b>Code</b> - 422 </summary>

**Description** -  Validation Error

**Example value**:

```json
 {
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
 }
```

</details>

</details>

<details>

<summary> POST <b>/users/{user_id}/documents/upload</b> Upload Document </summary>

##### **Description**

Uploading references.

##### **Parameters**

|name|description|
|---|---|
|user_id|0|

##### **Request body**

**Example value**:

```json
 {
  "file_path": "string"
 }
```

##### Responses

<details>

<summary> <b>Code</b> - 200 <summary>

**Description** - Successful Response

**Example value**:

```json
 {
  "output": {
    "fullName": "string",
    "position": "string",
    "salary": 0,
    "startDate": "string",
    "company": "string",
    "authenticity": "string",
    "authenticityConfidence": 0
  }
 }
```

</details>

<details>

<summary> <b>Code</b> - 422 <summary>

**Description** - Validation Error

**Example value**:

```json
 {
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
 }
```

</details>

</details>