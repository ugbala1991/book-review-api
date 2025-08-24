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


3.	Release Note**
We’re excited to announce the release of v1.5.0 of the Book Review API! This update brings important improvements in performance, bug fixes, and developer experience. It prepares the platform for future enhancements with a cleaner and more maintainable codebase.
Highlights
•	Core logic updated to improve stability and streamline workflows
•	Critical bug resolved in book detail rendering
•	Minor UI and user experience polish
•	Major internal refactoring of API routes for better maintainability
•	Project finalized for v1.5.0 release with documentation and cleanup

**Changelog in Markdown**
[v1.5.0] - 2025-08-20
Added
- Updated core functionality to improve reliability and performance
Fixed
- Resolved issue causing incorrect data rendering in book detail page
Changed
- Applied UI/UX improvements for enhanced user experience
- Cleaned and restructured codebase to remove redundancy

Refactored
- Refactored API route handlers for clarity and maintainability
Documentation
- Updated README with full API usage details and setup instructions
- Final project cleanup in preparation for production release
