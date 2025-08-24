# 📚 BOOK-REVIEW-API

A RESTful backend API for managing **books, users, and reviews**, built with **Node.js + Express + MongoDB**.  
This API allows users to **register, login, browse books, write reviews, and manage their profiles**.  



## 🚀 Features
- 🔐 User authentication with JWT
- 👤 User profile management
- 📚 Book catalog (CRUD)
- ✍️ User reviews & ratings
- 🌐 RESTful JSON API
- 🧪 Ready for testing with Postman/Insomnia


## 📂 Project Structure
├── src
│ ├── routes
│ │ ├── auth.js
│ │ ├── users.js
│ │ ├── books.js
│ │ └── reviews.js
│ ├── controllers
│ ├── models
│ └── index.js
├── package.json
└── README.md



## 🛠️ Installation & Setup

```bash
# Clone repository
git clone https://github.com/ugbala1991/book-review-api.git
cd book-review-api

# Install dependencies
npm install

# Setup environment variables
cp .env.example .env

# Run development server
npm run dev

Server runs on:
http://localhost:5000


**API Documentation**
1. Auth Routes
🔹 Register User

POST /api/auth/register

Request Body:
{
  "name": "Agbo Ugbala",
  "email": "ugbala@gmail.com",
  "password": "securePassword123"
}

Response:
{
  "message": "User registered successfully",
  "user": {
    "id": "123",
    "name": "Agbo Ugbala",
    "email": "ugbala@gmail.com"
  }
}

🔹 Login

POST /api/auth/login

Request Body:
{
  "email": "ugbala@gmail.com",
  "password": "securePassword123"
}

Response:
{
  "token": "<JWT_TOKEN>"
}


Book Routes
🔹 Get All Books

GET /api/books

Response:

[
  { "id": "1", "title": "The Great Gatsby", "author": "F. Scott Fitzgerald" },
  { "id": "2", "title": "1984", "author": "George Orwell" }
]

🔹 Get Book by ID

GET /api/books/:id

Response:

{
  "id": "1",
  "title": "The Great Gatsby",
  "author": "F. Scott Fitzgerald",
  "reviews": [
    { "userId": "123", "rating": 5, "comment": "A masterpiece." }
  ]
}

Review Routes
🔹 Add Review for a Book

POST /api/reviews/:bookId (Protected)

Request Body:
{
  "rating": 5,
  "comment": "Absolutely loved it!"
}

Response:
{ "message": "Review added successfully" }

🔹 Get Reviews for a Book

GET /api/reviews/:bookId

Response:

[
  { "userId": "123", "rating": 5, "comment": "Absolutely loved it!" },
  { "userId": "456", "rating": 4, "comment": "Great book." }
]



# 📦 Release Notes - BOOK-REVIEW-API


## v1.0.0 - Initial Release (2025-08-24)

### 🚀 Features
- Implemented **user authentication** (Register & Login with JWT).
- Added **User Profile API** (view & update own profile).
- Built **Book Management API**:
  - Create, Read, Update, Delete (CRUD) books.
  - Public access for browsing books.
- Added **Review System**:
  - Users can add, update, delete reviews.
  - Retrieve reviews per book.
- 🔐 Role-based access:
  - Admins can manage books.
  - Users can only manage their own reviews.
- 📖 Integrated **Swagger API Documentation** (`/api-docs`).

### 🛠️ Improvements
- Standardized **error handling** with JSON responses.
- Added middleware for **request validation** & **authentication**.
- Implemented project structure for **scalability**:
  - `routes/`, `controllers/`, `models/`.

### 🧪 Testing
- Added sample Postman collection for API testing.
- Basic Jest test setup for authentication and book endpoints.


## Upcoming (Planned)
- 📊 Ratings aggregation (average rating per book).
- 🖼️ Book cover image upload support.
- 📚 Pagination & filtering for books.
- 🔎 Full-text search for book titles/authors.




**Testing**

Run API tests with:

npm test
