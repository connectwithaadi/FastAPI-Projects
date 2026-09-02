# Todo Management API

A hands-on FastAPI Todo Management API built with Python, FastAPI, SQLAlchemy, SQLite, JWT authentication, and role-based authorization.

This project is part of my AI Engineer learning journey, where I'm building practical backend development skills before moving deeper into AI application development.

## 📌 Project Overview

This project demonstrates how to build a complete Todo Management backend using FastAPI. The application provides:

* User registration and authentication
* JWT-based authorization
* Password hashing
* User-specific Todo management
* Admin-level Todo management
* SQLAlchemy ORM
* SQLite database
* Request validation using Pydantic
* Modular API routers

The application currently uses SQLite as its database, with SQLAlchemy handling database sessions and ORM operations. 

## 🏗️ Architecture

```text
                    ┌──────────────────┐
                    │     FastAPI      │
                    └────────┬─────────┘
                             │
              ┌──────────────┼──────────────┐
              │              │              │
              ▼              ▼              ▼
           Auth API       Todo API       User API
              │              │              │
              └──────────────┼──────────────┘
                             │
                             ▼
                       SQLAlchemy ORM
                             │
                             ▼
                         SQLite DB
```

The FastAPI application registers separate routers for authentication, Todos, admin functionality, and users. 

## 🗄️ Database Design

The project contains two main database models:

**Users**
```text
Users
├── id
├── email
├── username
├── first_name
├── last_name
├── hashed_password
├── is_active
└── role
```

**Todos**
```text
Todos
├── id
├── title
├── description
├── priority
├── complete
└── owner_id → Users.id
```

The `owner_id` field creates the relationship between Todos and Users through a foreign key. 

**Relationship**
```text
Users
   │
   │ 1
   │
   │
   │ N
   ▼
Todos
```

One User → Many Todos
Each Todo is associated with the authenticated user's ID when it is created. 

## 🔐 Authentication

The API implements authentication using:
* OAuth2 Password Flow
* JWT access tokens
* bcrypt password hashing
* Role information inside JWT

During login, the user's credentials are verified and an access token is generated containing the username, user ID, and role. 

```text
Username + Password
        │
        ▼
   Authenticate
        │
        ▼
    JWT Token
        │
        ▼
 Protected APIs
```

## 👤 User Management

Users can:
* Register
* Login
* Retrieve their profile
* Change their password

Password changes require verification of the existing password before the new password is stored as a bcrypt hash. 

## 📝 Todo Management

Authenticated users can perform CRUD operations on their own Todos.

* **Create:** `POST /todo`
* **Read All:** `GET /`
* **Read One:** `GET /todo/{todo_id}`
* **Update:** `PUT /todo/{todo_id}`
* **Delete:** `DELETE /todo/{todo_id}`

The Todo API validates fields such as title length, description length, and priority range. 

## 👑 Admin Features

The project also includes an admin router. Administrators can:
* View all Todos
* Delete any Todo

Access is restricted by checking the user's role from the authenticated JWT payload. 

```text
                 User
                  │
          ┌───────┴───────┐
          │               │
       Normal           Admin
          │               │
          ▼               ▼
   Own Todos        All Todos
```

## 📂 Project Structure

```text
Project 3 - Todo Management API/
│
├── routers/
│   ├── auth.py
│   ├── todos.py
│   ├── users.py
│   └── admin.py
│
├── Screenshots/
│   ├── architecture.png
│   ├── pgadmin_1.png
│   ├── pgadmin_2.png
│   ├── schema.png
│   ├── sqlite_db.png
│   ├── sqlite-todos-terminal.png
│   └── swagger_ui.png
│
├── database.py
├── models.py
├── main.py
├── todosapp.db
└── README.md
```

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| Python | Programming language |
| FastAPI | REST API framework |
| SQLAlchemy | ORM and database interaction |
| SQLite | Database |
| Pydantic | Request validation |
| JWT | Authentication |
| OAuth2 | Authentication flow |
| bcrypt | Password hashing |
| Swagger UI | API testing |

## 🧠 Concepts Learned

Through this project, I practiced:
* FastAPI application structure
* REST API development
* CRUD operations
* SQLAlchemy ORM
* Database sessions
* SQLite integration
* Primary Keys
* Foreign Keys
* One-to-Many relationships
* Pydantic validation
* Dependency Injection
* OAuth2 authentication
* JWT authorization
* Password hashing
* Role-based authorization
* Protected routes
* Modular routers
* Swagger/OpenAPI testing

## 🚀 Running the Project

**1. Install dependencies**
```bash
pip install fastapi uvicorn sqlalchemy passlib python-jose python-multipart
```

**2. Start the API**
```bash
uvicorn main:app --reload
```

**3. Open Swagger UI**
Open: `http://127.0.0.1:8000/docs`

From Swagger UI you can test authentication, user management, Todo CRUD operations, and admin endpoints.

## 🔄 Project Progression

This project is intentionally structured as the foundation for the next database-focused upgrade.

```text
Project 3
Todo Management API
        │
        ▼
SQLite + SQLAlchemy
        │
        ▼
Project 3.5
Database Migration
        │
        ▼
Alembic + PostgreSQL
```

Project 3.5 will introduce Alembic for proper database schema migrations, rather than relying on `Base.metadata.create_all()` as used in the current project. 

## 🎯 Purpose

The goal of this project is to build a solid understanding of backend APIs, authentication, ORM-based database interaction, and relational data modeling using FastAPI.

It serves as the base Todo application that will later be extended with Alembic migrations and PostgreSQL in Project 3.5.
