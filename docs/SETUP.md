# *AI-Automation-for-Employment-Certificate-Processing* Setup and Usage Guide

## Prerequisites

Before setting up *AI-Automation-for-Employment-Certificate-Processing*, ensure you have the following installed:

<mark> to write docker version we use</mark>
- **python** (version 3.10)
- **Docker** (version ___)
- **PostgreSQL** (version 12 or higher)
- **Git**

## Quick Start

### 1. Clone the Repository

```bash
git clone <repository-url>
cd AI-Automation-for-Employment-Certificate-Processing
```

### 2. Environment Configuration

Create a `.env` file in the root directory:

```bash
SECRET_KEY=your_secret_key

# Database Configuration
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_SERVER=db
POSTGRES_PORT=5432
POSTGRES_DB=postgres
```

### 3. Database Setup

#### Option A: Using Docker (Recommended)

<mark> to be updated </mark>

```bash

```

#### Option B: Local PostgreSQL Installation

<mark> to be updated </mark>

1. Install PostgreSQL on your system
2. Create a database:
   ```sql
   CREATE DATABASE ___;
   ```

#### Initialize Database Schema

<mark> to be updated </mark>

```bash
# Run the database initialization script
psql -h localhost -U postgres -d ___ -f db/init/init.sql
```

### 4. Install Dependencies

<mark> maybe it's not necessary? </mark>

```bash
# Install python dependencies
cd Backend
python -m pip install -r requirements.txt
```

### 5. Run the Backend

```powershell
# From the Backend directory
docker compose up
```

The server will start on `http://localhost:8000`

## Project Structure

<mark> update </mark>

```bash
AI-Automation-for-Employment-Certificate-Processing/   # Main project repository
├── Backend/                                         # Backend module
│   ├── .github/                                     # GitHub configuration
│   │   └── workflows/                               # CI workflows
│   ├── backend/                                     # Source code for backend
│   ├── tests/                                       # Backend tests
│   ├── .env.template                                # Environment variables template
│   ├── .gitignore                                   # Files ignored by Git
│   ├── DOCUMENTATION.md                             # Backend documentation
│   ├── Dockerfile                                   # Docker image definition
│   ├── README.md                                    # Overview of backend module
│   ├── alembic.ini                                  # Database migration configuration
│   ├── docker-compose.yml                           # Docker Compose setup for backend
│   └── requirements.txt                             # Python dependencies
├── Bot/                                             # Bot module
│   ├── .github/                                     # GitHub configuration
│   │   └── workflows/                               # CI workflows
│   ├── bot/                                         # Source code for bot
│   ├── tests/                                       # Bot tests
│   ├── .dockerignore                                # Files ignored by Docker
│   ├── .env.template                                # Environment variables template
│   ├── .gitignore                                   # Files ignored by Git
│   ├── DOCUMENTATION.md                             # Bot documentation
│   ├── Dockerfile                                   # Docker image definition
│   ├── LAUNCH&ACCESS INSTRUCTIONS.md                # Bot launch instructions
│   ├── README.md                                    # Overview of bot module
│   ├── docker-compose.yml                           # Docker Compose setup for bot
│   └── requirements.txt                             # Python dependencies
├── docs/                                            # Project-wide documentation
├── .env.template                                    # Environment variables template for project
├── .gitignore                                       # Files ignored by Git at root
├── .gitmodules                                      # Git submodule configurations
├── README.md                                        # Project overview
└── docker-compose.yaml                              # Docker Compose setup for all modules


```

## API Testing

After running the Backend you can test the API by accessing to swagger using `http://localhost:8000/docs`

## Development

We have 4 repositories and each of them you can launch using Docker Compose

### Database Migrations

For database schema changes, create migration files in `db/migrations/`:

### Testing

```bash
# Run all tests
pytest
```

## Production Deployment

### Environment Variables

<mark> need to be checked </mark>

Set the following environment variables for production:

```bash
# Database
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_SERVER=db
POSTGRES_PORT=5432
POSTGRES_DB=postgres

# Secret key
SECRET_KEY=___
```

### Using Docker

```bash
# Build the application
docker build -t ___ .

# Run with Docker Compose
docker-compose up -d
```

### Using Docker Compose

```bash
# Start all services
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Ask for a pull request

## License

