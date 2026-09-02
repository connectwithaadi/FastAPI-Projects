# 🚀 Todo Management API — Alembic Database Migration

A hands-on database migration project demonstrating how to manage and version database schema changes using **Alembic** with a **FastAPI Todo Management API**.

This project is an extension of the Todo Management API and focuses on introducing a proper **database migration workflow** using Alembic instead of relying only on automatic table creation.

---

## 📌 Project Overview

In the previous Todo Management API project, the application used **SQLAlchemy** with a SQLite database.

In this project, **Alembic** is introduced to manage database schema changes through version-controlled migration files.

The project demonstrates how to:

- Install and configure Alembic
- Initialize an Alembic environment
- Connect Alembic with SQLAlchemy models
- Generate migration revisions
- Apply database migrations
- Roll back migrations
- Upgrade and downgrade database schemas
- Add new columns through migrations
- Maintain database schema history

---

## 🔄 Migration Workflow

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

Instead of manually modifying the database whenever the models change, Alembic keeps track of those changes through migration revisions.

---

## 🛠️ Technologies Used

| Technology | Purpose |
| :--- | :--- |
| **Python** | Programming language |
| **FastAPI** | REST API framework |
| **SQLAlchemy**| ORM and database interaction |
| **Alembic** | Database schema migration |
| **SQLite** | Development database |
| **Pydantic** | Data validation |
| **JWT** | Authentication |
| **OAuth2** | Authentication flow |
| **bcrypt** | Password hashing |

---

## 🗂️ Project Structure

```text
TodoApp/
│
├── alembic/
│   ├── versions/
│   │   └── <migration_files>.py
│   │
│   ├── env.py
│   ├── README
│   └── script.py.mako
│
├── routers/
│   ├── admin.py
│   ├── auth.py
│   ├── todos.py
│   └── users.py
│
├── fastapienv/
│
├── alembic.ini
├── database.py
├── main.py
├── models.py
├── todosapp.db
└── README.md
```

---

## 🧩 Alembic Components

### `alembic.ini`
The main Alembic configuration file.
It contains configuration required by Alembic to locate the migration environment and database connection settings.

### `alembic/env.py`
The migration environment configuration.
It connects Alembic with the application's SQLAlchemy metadata so that model changes can be detected while generating revisions.

### `alembic/versions/`
This directory contains the individual migration revision files.
Each revision represents a specific database schema change.

**Example:**
```text
alembic/
└── versions/
    ├── revision_001.py
    ├── revision_002.py
    └── revision_003.py
```

---

## 📝 Alembic Revision

A migration revision contains two important functions:

```python
def upgrade():
    pass

def downgrade():
    pass
```

### Upgrade
Applies the schema change to the database.
```text
Revision
   ↓
upgrade()
   ↓
Database updated
```

### Downgrade
Reverts the schema change.
```text
Database
   ↓
downgrade()
   ↓
Previous schema
```

---

## ⬆️ Database Upgrade

Alembic can apply pending migrations using:

```bash
alembic upgrade head
```

This moves the database to the latest available revision.

```text
Revision 1
    ↓
Revision 2
    ↓
Revision 3
    ↓
  HEAD
```

---

## ⬇️ Database Downgrade

A migration can also be rolled back:

```bash
alembic downgrade -1
```

This moves the database back by one revision.

```text
  HEAD
   ↓
Revision 3
   ↓
Revision 2
```

---

## 🆕 Creating a Revision

A new migration revision can be generated with:

```bash
alembic revision --autogenerate -m "migration message"
```

Alembic compares the SQLAlchemy models with the current database schema and generates a migration revision.

**Example:**
```bash
alembic revision --autogenerate -m "create phone number column"
```

---

## 📱 Migration Example

One of the schema changes demonstrated in this project is adding a `phone_number` field to the user model.

**Before Migration**
```text
Users
├── id
├── email
├── username
├── first_name
├── last_name
├── hashed_password
└── is_active
```

**After the migration:**
```text
Users
├── id
├── email
├── username
├── first_name
├── last_name
├── hashed_password
├── is_active
└── phone_number
```
The migration allows this schema change to be applied without manually recreating the database.

---

## 🔁 Migration Versioning

Alembic maintains a history of database changes.

```text
Database Schema
       │
       ▼
  Revision 1
       │
       ▼
  Revision 2
       │
       ▼
  Revision 3
       │
       ▼
Current Schema
```

This provides a structured way to track how the database schema evolved over time.

---

## 🧠 Concepts Learned

Through this project, I practiced:

- **Alembic fundamentals**
- **Alembic installation**
- **Alembic environment setup**
  - `alembic.ini`
  - `env.py`
- **Migration revisions**
- **Migration versioning**
  - `upgrade`
  - `downgrade`
- **Schema changes**
- **Auto-generated migrations**
- **SQLAlchemy metadata**
- **Database schema evolution**
- **Adding new columns through migrations**
- **Rolling back database changes**

---

## 🚀 Running the Project

**1. Activate Virtual Environment**
```bash
fastapienv\Scripts ctivate
```

**2. Start the FastAPI application**
```bash
uvicorn main:app --reload
```

**3. Run Alembic Migration**  
To apply all migrations:
```bash
alembic upgrade head
```

**4. Check Migration History**
```bash
alembic history
```

**5. Check Current Revision**
```bash
alembic current
```

**6. Roll Back One Migration**
```bash
alembic downgrade -1
```

---

## 📊 Project Progression

This project builds directly on the previous Todo Management API.

```text
       Project 3
  Todo Management API
           │
           ▼
FastAPI + SQLAlchemy + SQLite
           │
           ▼
      Project 3.5
Alembic Database Migration
           │
           ▼
   Schema Versioning
           │
           ▼
  Upgrade / Downgrade
           │
           ▼
      Project 4+
More Advanced Backend & Database Development
```

---

## 🎯 Purpose

The goal of this project is to understand how real backend applications manage database schema changes over time.

Instead of deleting and recreating database tables whenever a model changes, Alembic provides a controlled migration system where every schema modification is represented by a versioned migration.

This project strengthens the backend foundation required for building production-ready APIs and AI applications.

---

## 📚 Learning Section

This project covers the following Alembic topics:

- Alembic Data Migration Overview
- Alembic Introduction
- Installation and Setup
- Revisions
- Revision Upgrade
- Revision Downgrade
- Alembic Assignment
- Alembic Solution
