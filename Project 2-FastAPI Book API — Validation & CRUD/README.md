# 🚀 FastAPI Book API — Validation & CRUD

A hands-on FastAPI project focused on building a **Book Management REST API** using Pydantic validation, CRUD operations, path parameters, query parameters, HTTP status codes, and exception handling.

---

## ✨ Features

- 📚 Fetch all books
- 🔍 Fetch a book by ID
- ⭐ Filter books by rating
- 📅 Filter books by published date
- ➕ Create a new book
- ✏️ Update an existing book
- 🗑️ Delete a book
- ✅ Request body validation using Pydantic
- 🔢 Path parameter validation
- 🔎 Query parameter validation
- 🚦 HTTP status code handling
- ⚠️ Exception handling using `HTTPException`
- 📖 Interactive API documentation using Swagger UI

---

## 🛠️ Technologies Used

- Python
- FastAPI
- Pydantic
- Uvicorn

---

## 🔗 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/books` | Get all books |
| `GET` | `/books/{book_id}` | Get a book by ID |
| `GET` | `/books/?book_rating=5` | Filter books by rating |
| `GET` | `/books/publish/?published_date=2030` | Filter books by published date |
| `POST` | `/create-book` | Create a new book |
| `PUT` | `/books/update_book` | Update an existing book |
| `DELETE` | `/books/{book_id}` | Delete a book |

---

## 📦 Book Data Model

Each book contains:

| Field | Type | Validation |
|---|---|---|
| `id` | `int` | Optional when creating a book |
| `title` | `str` | Minimum 3 characters |
| `author` | `str` | Minimum 1 character |
| `description` | `str` | 1–100 characters |
| `rating` | `int` | Between 1 and 5 |
| `published_date` | `int` | Between 1997 and 2033 |

---

## 📖 Concepts Covered

### 1. Pydantic Validation

The `BookRequest` model validates incoming request data using Pydantic.

```python
class BookRequest(BaseModel):
    id: Optional[int] = Field(
        description="ID is not needed to create",
        default=None
    )
    title: str = Field(min_length=3)
    author: str = Field(min_length=1)
    description: str = Field(min_length=1, max_length=100)
    rating: int = Field(gt=0, lt=6)
    published_date: int = Field(gt=1997, lt=2033)
```

### 2. Path Parameters
Book IDs are received through the URL and validated using `Path()`.

```python
async def read_book(book_id: int = Path(gt=0)):
```
The ID must be greater than 0.

### 3. Query Parameters
The API supports filtering books using query parameters.

**Example:**
```http
GET /books/?book_rating=5
```
Rating validation is handled using:

```python
book_rating: int = Query(gt=0, lt=6)
```

### 4. CRUD Operations
The API implements the four basic CRUD operations:
- **Create** → `POST`
- **Read** → `GET`
- **Update** → `PUT`
- **Delete** → `DELETE`

### 5. HTTP Status Codes
The project uses appropriate HTTP status codes such as:

```python
status.HTTP_200_OK
status.HTTP_201_CREATED
status.HTTP_204_NO_CONTENT
```

### 6. Exception Handling
`HTTPException` is used when a requested book does not exist.

```python
raise HTTPException(
    status_code=404,
    detail="Item not found"
)
```
This provides a proper error response to the client.

### 7. Automatic ID Generation
New books receive an ID automatically based on the existing books.

```python
book.id = 1 if len(BOOKS) == 0 else BOOKS[-1].id + 1
```

## 🧪 Testing with Swagger UI
FastAPI automatically provides interactive API documentation through Swagger UI.
After starting the application, open:

```
http://127.0.0.1:8000/docs
```
The Swagger UI can be used to execute and test all available API endpoints directly from the browser.

*API Documentation* | *API Response*

## ▶️ How to Run

1. **Install Dependencies**
```bash
pip install fastapi uvicorn
```

2. **Start the Application**
```bash
uvicorn book:app --reload
```

3. **Open Swagger UI**
Navigate to: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

## 📂 Project Structure

```text
Project 2- Move Fast with FastAPI/
│
├── book.py
├── README.md
├── swagger-ui.png
└── api-response.png
```

## 📌 Learning Outcome
Through this project, I practiced:

- FastAPI application setup
- Pydantic models and validation
- Request body validation (`Field()` constraints)
- Path parameters
- Query parameters
- CRUD operations
- HTTP status codes
- `HTTPException` and basic API error handling
- Automatic ID generation
- Swagger UI API testing

## 🚀 Project Summary
This project strengthened my understanding of building validated REST APIs with FastAPI and provided practical experience with request validation, CRUD operations, API parameters, and HTTP error handling.
