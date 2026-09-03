# 🧪 Project 4 — FastAPI Unit & Integration Testing

A hands-on FastAPI project focused on **Unit Testing and Integration Testing** using **Pytest**.

This project builds on the Todo Management API and introduces automated testing for FastAPI routes, authentication, dependencies, and CRUD operations.

The goal of this project is to understand how to write, organize, and execute tests for a real FastAPI application.

---

## 🚀 Project Overview

This project covers the fundamentals of testing a FastAPI application using **Pytest** and FastAPI's **TestClient**.

The testing setup includes:

- Unit testing with Pytest
- Integration testing for FastAPI endpoints
- Testing FastAPI routes
- Testing authentication
- Testing dependencies
- Testing CRUD operations
- Testing authenticated and unauthenticated requests
- Organizing tests into separate test modules

---

## 🛠️ Technologies Used

- Python
- FastAPI
- Pytest
- SQLAlchemy
- SQLite
- Pydantic
- FastAPI TestClient
- Alembic

---

## 📂 Project Structure

```text
Project 4 - Unit & Integration Testing/
│
├── test/
│   ├── __init__.py
│   ├── test_admin.py
│   ├── test_auth.py
│   ├── test_example.py
│   ├── test_main.py
│   ├── test_todos.py
│   ├── test_users.py
│   └── utils.py
│
├── routers/
│   ├── admin.py
│   ├── auth.py
│   ├── todos.py
│   └── users.py
│
├── alembic/
│
├── database.py
├── main.py
├── models.py
├── alembic.ini
└── README.md
```

---

## 🧪 Testing Topics Covered

### Pytest Basics
- Creating test functions
- Assertions
- Running tests with Pytest
- Organizing test files

### FastAPI Testing
- Using TestClient
- Testing API endpoints
- Checking HTTP status codes
- Validating JSON responses

### Dependency Testing
- Setting up test dependencies
- Dependency overrides
- Creating isolated testing environments

### Authentication Testing
- Testing login functionality
- Testing authenticated requests
- Testing unauthorized requests
- Testing user authentication dependencies

### CRUD Testing
Tests are written for core Todo and User functionality, including:
- Create
- Read
- Update
- Delete
- Complete Todo
- User-related operations

---

## ▶️ Running the Project

1. **Create and activate virtual environment**
```bash
python -m venv fastapienv
```
Activate the environment (Windows):
```bash
fastapienv\Scripts\activate
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Run the FastAPI application**
```bash
uvicorn main:app --reload
```

4. **Run the test suite**  
From the project root:
```bash
pytest
```
To get more detailed output:
```bash
pytest -v
```

---

## 📊 Testing

The project contains separate test modules for different parts of the FastAPI application.

```text
test/
├── test_admin.py
├── test_auth.py
├── test_main.py
├── test_todos.py
└── test_users.py
```
This structure keeps tests organized according to the functionality being tested.

---

## 🎯 Learning Objectives

Through this project, I learned how to:

- Write unit tests using Pytest
- Write integration tests for FastAPI
- Test FastAPI endpoints using TestClient
- Test HTTP status codes and JSON responses
- Test authentication flows
- Test FastAPI dependencies
- Override dependencies during testing
- Test CRUD functionality
- Organize a test suite for a backend application

---

## 📌 Project Highlights

- 🧪 **Pytest-based testing**
- ⚡ **FastAPI TestClient**
- 🔐 **Authentication testing**
- 🔄 **CRUD endpoint testing**
- 🔗 **Dependency testing**
- 🗄️ **Database testing**
- 📁 **Organized test structure**
- 🛠️ **Unit & Integration Testing**

---

## 🎓 Learning Journey

This project is part of my AI Engineer learning journey.
The progression of my FastAPI projects:

1. **Project 1** — FastAPI Request Methods  
   ↓  
2. **Project 2** — FastAPI Book API & Validation  
   ↓  
3. **Project 3** — Todo Management API  
   ↓  
4. **Project 3.5** — Alembic Data Migration  
   ↓  
5. **Project 4** — Unit & Integration Testing  

*The next step is to build a Full Stack FastAPI Application with frontend integration.*

---

## 👨‍💻 Author

**Aditya Kumar Singh**  
