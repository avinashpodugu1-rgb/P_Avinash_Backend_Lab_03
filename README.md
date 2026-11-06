# BDF Lab 3 - REST API, Query Parameters, Validation & Debugging

**Name: ** P.Avinash
** Registration: **252U1R1194
** Class & sec: ** CSE-2D

Complete Node.js + Express + SQLite implementation of Lab 3.

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/avinashpodugu1-rgb/P_Avinash_Backend_Lab_03)

---

## 🌐 Live Deployed API (Render)

- **Primary Live Base URL:** [https://p-avinash-backend-lab-03.onrender.com/](https://p-avinash-backend-lab-03.onrender.com/)
- **Deployment Status:** Active 🟢

### 📚 Live Endpoint Links (Click to test directly in browser)

| Action | Method | Live Endpoint URL |
|---|---|---|
| **API Root & Directory** | `GET` | [https://p-avinash-backend-lab-03.onrender.com/](https://p-avinash-backend-lab-03.onrender.com/) |
| **Get All Books (Default)** | `GET` | [https://p-avinash-backend-lab-03.onrender.com/books](https://p-avinash-backend-lab-03.onrender.com/books) |
| **Get Single Book (ID: 1)** | `GET` | [https://p-avinash-backend-lab-03.onrender.com/books/1](https://p-avinash-backend-lab-03.onrender.com/books/1) |
| **Get Single Book (ID: 2)** | `GET` | [https://p-avinash-backend-lab-03.onrender.com/books/2](https://p-avinash-backend-lab-03.onrender.com/books/2) |

---

### 🔍 Query Parameter Filtering, Searching & Pagination

| Feature | Query Params | Direct Live URL |
|---|---|---|
| **Search by Title** | `?search_q=the` | [https://p-avinash-backend-lab-03.onrender.com/books?search_q=the](https://p-avinash-backend-lab-03.onrender.com/books?search_q=the) |
| **Sort by Price (Ascending)** | `?order_by=price&order=ASC` | [https://p-avinash-backend-lab-03.onrender.com/books?order_by=price&order=ASC](https://p-avinash-backend-lab-03.onrender.com/books?order_by=price&order=ASC) |
| **Sort by Price (Descending)** | `?order_by=price&order=DESC` | [https://p-avinash-backend-lab-03.onrender.com/books?order_by=price&order=DESC](https://p-avinash-backend-lab-03.onrender.com/books?order_by=price&order=DESC) |
| **Sort by Title (Descending)** | `?order_by=title&order=DESC` | [https://p-avinash-backend-lab-03.onrender.com/books?order_by=title&order=DESC](https://p-avinash-backend-lab-03.onrender.com/books?order_by=title&order=DESC) |
| **Pagination (First 5 books)** | `?limit=5&offset=0` | [https://p-avinash-backend-lab-03.onrender.com/books?limit=5&offset=0](https://p-avinash-backend-lab-03.onrender.com/books?limit=5&offset=0) |
| **Pagination (Next 5 books)** | `?limit=5&offset=5` | [https://p-avinash-backend-lab-03.onrender.com/books?limit=5&offset=5](https://p-avinash-backend-lab-03.onrender.com/books?limit=5&offset=5) |
| **Price Range (₹100 to ₹500)** | `?min_price=100&max_price=500` | [https://p-avinash-backend-lab-03.onrender.com/books?min_price=100&max_price=500](https://p-avinash-backend-lab-03.onrender.com/books?min_price=100&max_price=500) |
| **Price (₹300 or more)** | `?min_price=300` | [https://p-avinash-backend-lab-03.onrender.com/books?min_price=300](https://p-avinash-backend-lab-03.onrender.com/books?min_price=300) |
| **Price (Under ₹400)** | `?max_price=400` | [https://p-avinash-backend-lab-03.onrender.com/books?max_price=400](https://p-avinash-backend-lab-03.onrender.com/books?max_price=400) |
| **Combined Query** | `?search_q=the&order_by=price&order=DESC&min_price=200&max_price=600&limit=5&offset=0` | [https://p-avinash-backend-lab-03.onrender.com/books?search_q=the&order_by=price&order=DESC&min_price=200&max_price=600&limit=5&offset=0](https://p-avinash-backend-lab-03.onrender.com/books?search_q=the&order_by=price&order=DESC&min_price=200&max_price=600&limit=5&offset=0) |

---

### ⚠️ Live Validation & Error Response Links

Click these links in your browser to verify the consistent `{ "message": "..." }` error formatting live on Render:

| Error Case | HTTP Status | Direct Live Test Link |
|---|---|---|
| **Book Not Found** | `404 Not Found` | [https://p-avinash-backend-lab-03.onrender.com/books/99999](https://p-avinash-backend-lab-03.onrender.com/books/99999) |
| **Invalid ID Format** | `400 Bad Request` | [https://p-avinash-backend-lab-03.onrender.com/books/abc](https://p-avinash-backend-lab-03.onrender.com/books/abc) |
| **Invalid Sort Column** | `400 Bad Request` | [https://p-avinash-backend-lab-03.onrender.com/books?order_by=invalid](https://p-avinash-backend-lab-03.onrender.com/books?order_by=invalid) |
| **Invalid Sort Direction** | `400 Bad Request` | [https://p-avinash-backend-lab-03.onrender.com/books?order=SIDEWAYS](https://p-avinash-backend-lab-03.onrender.com/books?order=SIDEWAYS) |
| **Invalid Limit (< 1)** | `400 Bad Request` | [https://p-avinash-backend-lab-03.onrender.com/books?limit=0](https://p-avinash-backend-lab-03.onrender.com/books?limit=0) |
| **Invalid Price Range** | `400 Bad Request` | [https://p-avinash-backend-lab-03.onrender.com/books?min_price=500&max_price=100](https://p-avinash-backend-lab-03.onrender.com/books?min_price=500&max_price=100) |
| **Undefined Route** | `404 Not Found` | [https://p-avinash-backend-lab-03.onrender.com/unknown-route](https://p-avinash-backend-lab-03.onrender.com/unknown-route) |

---

### ✍️ Live Write Endpoints (`POST`, `PUT`, `DELETE`)

- **Create Book (`POST /books`):**
  - **Live URL:** `https://p-avinash-backend-lab-03.onrender.com/books`
  - **Headers:** `Content-Type: application/json`
  - **Body:**
    ```json
    {
      "title": "JavaScript Basics",
      "author": "John",
      "price": 350
    }
    ```
- **Update Book (`PUT /books/:id`):**
  - **Live URL:** `https://p-avinash-backend-lab-03.onrender.com/books/1`
  - **Body:**
    ```json
    {
      "title": "Updated Book Title",
      "author": "Updated Author",
      "price": 299
    }
    ```
- **Delete Book (`DELETE /books/:id`):**
  - **Live URL:** `https://p-avinash-backend-lab-03.onrender.com/books/1`

---

## 💻 Local Quick Start

### 1. Install Dependencies
```bash
cd lab-03-rest-api
npm install
```

### 2. Start the Server
```bash
npm start
```
The server will start locally at `http://localhost:3000`.

## Features Implemented
- **CRUD REST API**: Full set of endpoints on `/books` (`GET /`, `GET /books`, `GET /books/:id`, `POST /books`, `PUT /books/:id`, `DELETE /books/:id`).
- **Query Parameter Filtering & Pagination**: Supports `search_q`, `order_by`, `order`, `min_price`, `max_price`, `limit`, and `offset`.
- **Validation**: Strict POST/PUT body validation for `title`, `author`, and numeric `price` (rejects negative prices and empty values).
- **Consistent Response Format**: All error responses return `{ "message": "..." }` with appropriate status codes (`400`, `404`, `500`).
- **SQLite Database**: Auto-created and seeded with 10 sample books on first launch.
- **Postman Collection & Tests**: Pre-configured collection with 21 automated test cases.

For complete documentation and screenshots, refer to [`lab-03-rest-api/README.md`](./lab-03-rest-api/README.md).
