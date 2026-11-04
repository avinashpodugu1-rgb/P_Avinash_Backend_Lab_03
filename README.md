# BDF Lab 3 - REST API, Query Parameters, Validation & Debugging

Complete Node.js + Express + SQLite implementation of Lab 3.

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/avinashpodugu1-rgb/P_Avinash_Backend_Lab_03)

## Quick Start

### 1. Install Dependencies
```bash
cd lab-03-rest-api
npm install
```

### 2. Start the Server
```bash
npm start
```
Or from the project root:
```bash
npm start
```
The server will start at `http://localhost:3000`.

## Features Implemented
- **CRUD REST API**: Full set of endpoints on `/books` (`GET /`, `GET /books`, `GET /books/:id`, `POST /books`, `PUT /books/:id`, `DELETE /books/:id`).
- **Query Parameter Filtering & Pagination**: Supports `search_q`, `order_by`, `order`, `min_price`, `max_price`, `limit`, and `offset`.
- **Validation**: Strict POST/PUT body validation for `title`, `author`, and numeric `price` (rejects negative prices and empty values).
- **Consistent Response Format**: All error responses return `{ "message": "..." }` with appropriate status codes (`400`, `404`, `500`).
- **SQLite Database**: Auto-created and seeded with 10 sample books on first launch.
- **Postman Collection & Tests**: Pre-configured collection with 21 automated test cases.

For complete documentation and screenshots, refer to [`lab-03-rest-api/README.md`](./lab-03-rest-api/README.md).

