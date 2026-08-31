# 📚 FastAPI Request Method Logic

A beginner-friendly FastAPI project focused on understanding **HTTP request methods, API endpoints, path parameters, query parameters, and basic CRUD operations**.

This project was built as **Project 1** while learning FastAPI.

---

## 🎯 Project Objective

The main goal of this project is to understand how FastAPI handles different HTTP request methods and how data can be fetched, filtered, created, updated, and deleted through API endpoints.

---

## 🛠️ Technologies Used

- Python
- FastAPI
- Uvicorn

---

## 📂 Project Structure

```text
Project 1- FastAPI Request Method Logic/
│
├── book.py
├── README.md
├── swagger-ui.png
└── get-books-response.png
```
## 🚀 Features

- Fetch all books
- Fetch a specific book using a path parameter
- Filter books using query parameters
- Filter books by author
- Create a new book
- Update an existing book
- Delete a book
- Interactive API documentation using Swagger UI

---

## 🔗 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/books` | Get all books |
| `GET` | `/books/mybook` | Get a sample favorite book |
| `GET` | `/books/{book_title}` | Get a book by title |
| `GET` | `/books/?category=science` | Filter books by category |
| `GET` | `/books/{book_author}/?category=maths` | Filter books by author and category |
| `POST` | `/books/create_book` | Create a new book |
| `PUT` | `/books/update_book` | Update an existing book |
| `DELETE` | `/books/delete_book/{book_title}` | Delete a book |
| `GET` | `/books/byauthor/{author}` | Get books by author |

---

## 📖 Concepts Covered

### 1. GET Request

Used to retrieve data from the API.

Example:

```http
GET /books
```
Returns the complete list of books.

### 2. Path Parameters
Path parameters are used to pass values directly through the URL.

**Example:**
```http
GET /books/Title One
```
The `book_title` parameter is used to find the matching book.

### 3. Query Parameters
Query parameters are used for filtering data.

**Example:**
```http
GET /books/?category=science
```
This returns books belonging to the `science` category.

### 4. POST Request
Used to create a new book.

```http
POST /books/create_book
```
The new book is received through the request body.

### 5. PUT Request
Used to update an existing book.

```http
PUT /books/update_book
```
The matching book is replaced with the updated book data.

### 6. DELETE Request
Used to remove a book.

```http
DELETE /books/delete_book/{book_title}
```
The book is searched by title and removed from the list.

## 🧪 Testing with Swagger UI
FastAPI automatically provides interactive API documentation.
After starting the application, open:

```
http://127.0.0.1:8000/docs
```
The Swagger UI allows the available endpoints to be executed and tested directly from the browser.

*API Documentation* | *GET Request Example*

## ▶️ How to Run

1. **Install FastAPI and Uvicorn**
```bash
pip install fastapi uvicorn
```

2. **Start the application**
From the project directory run:
```bash
uvicorn book:app --reload
```

3. **Open Swagger UI**
Navigate to: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)


## 📌 Learning Outcome
Through this project, I practiced:

- FastAPI application setup
- API endpoint creation
- HTTP request methods
- GET, POST, PUT, and DELETE operations
- Path parameters
- Query parameters
- Basic CRUD logic
- Filtering API data
- Testing APIs using Swagger UI

## 🚀 Next Step
This project is part of my FastAPI learning journey.
The next projects will build on these fundamentals by introducing more structured API development, error handling, databases, authentication, testing, and deployment.
