# 🚀 FastAPI Projects

A collection of hands-on **FastAPI backend projects** built as part of my **AI Engineer learning journey**.

This repository documents my progression from basic REST API concepts to more advanced backend development, including:

- REST API development
- Request & response handling
- Pydantic validation
- CRUD operations
- SQLAlchemy ORM
- Database design
- Authentication & authorization
- JWT & OAuth2
- Alembic database migrations
- Unit & Integration Testing
- Pytest
- Dependency Injection
- API testing with Swagger UI
- Web UI & Frontend Integration

The projects are intentionally built step-by-step so that each project introduces new backend concepts while building on the previous one.

---

## 📚 Repository Projects

| Project | Description | Main Concepts |
|---|---|---|
| [**Project 1 — FastAPI Request Method Logic**](https://github.com/connectwithaadi/FastAPI-Projects/tree/main/Project%201-%20FastAPI%20Request%20Method%20Logic) | Introduction to FastAPI and REST API fundamentals | HTTP Methods, Path Parameters, Query Parameters, CRUD |
| [**Project 2 — FastAPI Book API**](https://github.com/connectwithaadi/FastAPI-Projects/tree/main/Project%202-FastAPI%20Book%20API%20%E2%80%94%20Validation%20%26%20CRUD) | Validated REST API with CRUD functionality | Pydantic, Validation, Status Codes, HTTPException |
| [**Project 3 — Todo Management API**](https://github.com/connectwithaadi/FastAPI-Projects/tree/main/Project%203-Todo%20Management%20API) | Complete backend application with database and authentication | SQLAlchemy, SQLite, JWT, OAuth2, RBAC |
| [**Project 3.5 — Alembic Database Migration**](https://github.com/connectwithaadi/FastAPI-Projects/tree/main/Project%203.5-Alembic%20Database%20Migration) | Database schema versioning and migration workflow | Alembic, Revisions, Upgrade/Downgrade, Schema Evolution |
| [**Project 4 — Unit & Integration Testing**](https://github.com/connectwithaadi/FastAPI-Projects/tree/main/Project%204%20-FastAPI%20Unit%20%26%20Integration%20Testing) | Automated testing for the FastAPI application | Pytest, TestClient, Dependency Overrides, Integration Testing |
| [**Project 5 — Todo App with Web UI & Frontend Integration**](https://github.com/connectwithaadi/FastAPI-Projects/tree/main/Project%205-Todo%20App%20with%20Web%20UI%20%26%20Frontend%20Integration) | Full-stack Todo application with a server-rendered web interface | Jinja2, HTML, CSS, Bootstrap, JavaScript, Templates, Authentication |

---

# 🗂️ Project Details

## 1️⃣ Project 1 — FastAPI Request Method Logic

A beginner-friendly FastAPI project focused on understanding the fundamentals of building REST APIs.

### Concepts Covered

- FastAPI application setup
- HTTP request methods
  - `GET`
  - `POST`
  - `PUT`
  - `DELETE`
- Path parameters
- Query parameters
- Request bodies
- Basic CRUD operations
- Filtering API data
- Swagger UI

### Technologies

- Python
- FastAPI
- Uvicorn

### What I Learned

This project established the foundation for working with FastAPI endpoints and understanding how clients communicate with backend APIs.

---

## 2️⃣ Project 2 — FastAPI Book API — Validation & CRUD

A Book Management REST API focused on **request validation and structured CRUD operations**.

### Features

- Get all books
- Get book by ID
- Filter books by rating
- Filter books by published date
- Create books
- Update books
- Delete books
- Request validation
- Path parameter validation
- Query parameter validation
- HTTP status codes
- Exception handling
- Swagger API testing

### Concepts Covered

- Pydantic models
- `BaseModel`
- `Field()`
- `Path()`
- `Query()`
- CRUD operations
- `HTTPException`
- HTTP status codes
- Automatic ID generation

### Technologies

- Python
- FastAPI
- Pydantic
- Uvicorn

### What I Learned

This project introduced structured request validation and proper API error handling, moving beyond basic endpoint creation.

---

## 3️⃣ Project 3 — Todo Management API

A complete backend application implementing a **Todo Management System** with authentication, authorization, database persistence, and modular API routers.

### Features

- User registration
- User login
- JWT authentication
- OAuth2 password flow
- Password hashing
- User profile management
- Password change functionality
- User-specific Todo management
- Todo CRUD operations
- Admin Todo management
- Role-based authorization
- Protected API routes
- Pydantic validation
- SQLAlchemy ORM
- SQLite database

### Architecture

```text
                         FastAPI
                            │
            ┌───────────────┼───────────────┐
            │               │               │
            ▼               ▼               ▼
         Auth API        Todo API        User API
            │               │               │
            └───────────────┼───────────────┘
                            │
                            ▼
                     SQLAlchemy ORM
                            │
                            ▼
                        SQLite DB

Database Relationship
Users
  │
  │ 1
  │
  │ N
  ▼
Todos

Each Todo belongs to a specific authenticated user through a foreign key relationship.

Authentication Flow
Username + Password
        │
        ▼
   Authentication
        │
        ▼
    JWT Token
        │
        ▼
 Protected Routes
```

### Technologies

- Python
- FastAPI
- SQLAlchemy
- SQLite
- Pydantic
- JWT
- OAuth2
- bcrypt
- Swagger UI

### What I Learned
This project was a major step from simple APIs toward a real backend application, introducing databases, authentication, authorization, ORM-based development, and modular architecture.

---

## 3.5️⃣ Project 3.5 — Alembic Database Migration
An extension of the Todo Management API focused on database schema migration and version control using Alembic.
Instead of relying only on automatic table creation, this project introduces a structured migration workflow for managing database changes.

### Concepts Covered

- Alembic installation
- Alembic configuration
  - `alembic.ini`
  - `env.py`
- Migration revisions
- Migration versioning
  - `upgrade()`
  - `downgrade()`
- Auto-generated migrations
- SQLAlchemy metadata
- Schema evolution
- Adding new columns
- Migration history

### Migration Workflow
```text
SQLAlchemy Models
       │
       ▼
Alembic Revision
       │
       ▼
Migration File
       │
       ├──── upgrade()
       │
       └──── downgrade()
       │
       ▼
Database Schema
```

### Common Commands

- `alembic revision --autogenerate -m "migration message"`
- `alembic upgrade head`
- `alembic downgrade -1`
- `alembic history`
- `alembic current`

### Technologies

- Python
- FastAPI
- SQLAlchemy
- Alembic
- SQLite
- Pydantic
- JWT
- OAuth2
- bcrypt

### What I Learned
This project introduced an important production backend concept: database schema versioning.
It demonstrates how database changes can be tracked, applied, and rolled back through version-controlled migration files.

---

## 4️⃣ Project 4 — FastAPI Unit & Integration Testing
A testing-focused FastAPI project introducing automated testing using Pytest and FastAPI's TestClient.
The project builds on the Todo Management API and tests its routes, authentication, dependencies, CRUD operations, and database-related functionality.

### Testing Areas

- Unit testing
- Integration testing
- Pytest fundamentals
- FastAPI TestClient
- API endpoint testing
- HTTP status code testing
- JSON response validation
- Authentication testing
- Unauthorized request testing
- Dependency testing
- Dependency overrides
- CRUD testing
- Database testing

### Test Structure
```text
test/
├── test_admin.py
├── test_auth.py
├── test_example.py
├── test_main.py
├── test_todos.py
├── test_users.py
└── utils.py
```

### Example Testing Flow
```text
Test Case
    │
    ▼
FastAPI TestClient
    │
    ▼
API Endpoint
    │
    ▼
Application Logic
    │
    ▼
Database
    │
    ▼
Response
    │
    ▼
Assertion
```

### Technologies

- Python
- FastAPI
- Pytest
- FastAPI TestClient
- SQLAlchemy
- SQLite
- Pydantic
- Alembic

### What I Learned
This project added automated testing to the backend development workflow and helped me understand how real FastAPI applications can be tested before deployment.

---

## 5️⃣ Project 5 — Todo App with Web UI & Frontend Integration
A full-stack Todo application that extends the previous Todo backend by adding a server-rendered Web UI and frontend integration.
This project demonstrates how FastAPI can be used not only to build APIs, but also to serve HTML pages and connect backend functionality with a user-facing web interface.

### 🚀 Features

- User registration
- User login
- Authentication
- Todo creation
- Todo listing
- Todo editing
- Todo management
- Protected pages
- Server-rendered HTML templates
- Jinja2 template integration
- Static CSS and JavaScript files
- Bootstrap-based UI
- Frontend and backend integration
- Database-backed Todo operations

### 🖥️ Web UI
The application provides a browser-based interface for interacting with the Todo backend.
- Login
- Registration
- Todo Dashboard
- Edit Todo

### 📂 Frontend Structure
```text
static/
├── css/
│   ├── base.css
│   └── bootstrap.css
│
└── js/
    ├── base.js
    ├── bootstrap.js
    ├── jquery-slim.js
    └── popper.js

templates/
├── add-todo.html
├── edit-todo.html
├── home.html
├── layout.html
├── login.html
├── navbar.html
├── register.html
└── todo.html
```

### 🏗️ Application Structure
```text
                    FastAPI
                       │
          ┌────────────┴────────────┐
          │                         │
          ▼                         ▼
      REST APIs                  Web UI
          │                         │
          │                    Jinja2 Templates
          │                         │
          └────────────┬────────────┘
                       ▼
                 Application Logic
                       │
                       ▼
                 SQLAlchemy ORM
                       │
                       ▼
                   SQLite DB
```

### 🛠️ Technologies

- Python
- FastAPI
- SQLAlchemy
- SQLite
- Pydantic
- Jinja2
- HTML
- CSS
- Bootstrap
- JavaScript
- JWT / Authentication
- Alembic

### 🧠 Concepts Learned
Through this project, I practiced:

- FastAPI web application development
- Jinja2 templates
- Template inheritance
- HTML form handling
- Static file serving
- Frontend and backend integration
- Authentication with web pages
- Database-backed web applications
- Reusing backend functionality through a web interface
- Organizing frontend assets in a FastAPI project

### What I Learned
This project helped me move from API-only backend development toward building a complete application where the FastAPI backend communicates with a browser-based frontend.
It also provided practical experience with the connection between:

```text
Frontend
   ↓
HTML Forms
   ↓
FastAPI Routes
   ↓
Business Logic
   ↓
SQLAlchemy
   ↓
Database
```

---

## 🧠 Skills Developed
Through these projects, I have developed practical experience with:

### FastAPI
- FastAPI application structure
- REST API development
- Routing
- Request handling
- Response handling
- Path parameters
- Query parameters
- Request bodies
- Dependency Injection
- Swagger / OpenAPI
- Jinja2 templates
- Static files

### API Development
- CRUD operations
- HTTP methods
- HTTP status codes
- Exception handling
- API validation
- Protected routes
- Modular routers
- Frontend/API integration

### Data Validation
- Pydantic BaseModel
- Field validation
- Query validation
- Path validation
- Request body validation

### Databases
- SQLAlchemy ORM
- SQLite
- Relational database concepts
- Primary keys
- Foreign keys
- One-to-many relationships
- Database sessions
- Schema management

### Authentication & Security
- OAuth2
- JWT authentication
- Password hashing
- Authentication dependencies
- Role-based authorization
- Protected endpoints

### Database Migrations
- Alembic
- Migration revisions
- Schema versioning
- Upgrade / downgrade workflow
- Auto-generated migrations

### Testing
- Pytest
- Unit testing
- Integration testing
- FastAPI TestClient
- Dependency overrides
- Authentication testing
- CRUD testing

### Frontend Integration
- HTML
- CSS
- Bootstrap
- JavaScript
- Jinja2
- Template inheritance
- Static assets
- Server-rendered pages
- Form-based frontend/backend communication

---

## 📈 Learning Progression
The projects follow a deliberate progression from basic API development to a complete web application.

```text
Project 1
FastAPI Fundamentals
        │
        ▼
Project 2
Validation + CRUD
        │
        ▼
Project 3
Database + Authentication
        │
        ▼
Project 3.5
Alembic + Schema Migration
        │
        ▼
Project 4
Unit + Integration Testing
        │
        ▼
Project 5
Web UI + Frontend Integration
        │
        ▼
Full Stack FastAPI Application
```
Each project adds another layer of backend engineering knowledge.

## 🏗️ Backend Development Journey
```text
                    REST APIs
                       │
                       ▼
                FastAPI Framework
                       │
                       ▼
             Pydantic Validation
                       │
                       ▼
                  CRUD Logic
                       │
                       ▼
                SQLAlchemy ORM
                       │
                       ▼
               Database Design
                       │
                       ▼
            Authentication & JWT
                       │
                       ▼
             Role-Based Access
                       │
                       ▼
             Alembic Migrations
                       │
                       ▼
             Automated Testing
                       │
                       ▼
             Web UI Integration
                       │
                       ▼
              Full Stack Backend
```

## 🎯 Repository Goal
The goal of this repository is to build strong backend engineering fundamentals using FastAPI before moving deeper into AI Engineering.
Rather than only following tutorials, these projects provide hands-on experience with progressively more realistic backend systems.
The long-term objective is to be able to build APIs and backend systems that can serve as the foundation for:

- AI applications
- Machine Learning systems
- LLM applications
- RAG pipelines
- AI agents
- Data-driven applications
- Production web applications

## 🛠️ Development Approach
The projects follow a practical learning approach:

```text
Learn Concept
     │
     ▼
Implement
     │
     ▼
Build Project
     │
     ▼
Test
     │
     ▼
Document
     │
     ▼
Push to GitHub
```

This repository therefore serves both as a learning record and as a portfolio of backend development work.
