# 📚 Online Book Store SQL Project

## 📌 Project Overview
This project demonstrate SQL-based **Online Book Store Management System** developed using **PostgreSQL**. It includes database creation, table relationships, data manipulation, and analytical SQL queries to generate meaningful business insights.

The project showcases practical SQL skills used in real-world data analytics and business intelligence.

### Key Objectives

- Design a relational database
- Manage books, customers, and orders data
- Perform sales and customer analysis
- Generate business insights using SQL

---
## ✨ Key Features

- Relational database design
- Primary & Foreign Key relationships
- CRUD operations using SQL
- Sales and customer analysis
- Revenue and stock analysis
- Business-oriented SQL queries

---
## 🛠️ Tech Stack

- PostgreSQL – Database management
- DDL – Database/table creation and modification
- DML – Insert, update, and delete operations
- DQL – Data retrieval using SELECT
- pgAdmin 4 – PostgreSQL database administration

---
## 📷 Repository Structure

```
Online-Book-Store-Project
│
├── Dataset/
│   ├── Books.csv
│   ├── Customers.csv
│   └── Orders.csv
│   
├── screenshot/
|   ├── 5 most expensive books.png
|   ├── Highest spending customer.png
|   ├── book sold based on gemre.png
|   ├── books with lowest stock.png
|   ├── most frequently order book.png
|
├── ERD of online book store.png 
└── README.md
```
---

## 📂 Database Schema(ER Diagram)
<img width="958" height="586" alt="ERD of online book store" src="https://github.com/user-attachments/assets/e5e271d2-9891-4993-9f6c-de70131fa4ce" />
---

## 📷 Sample Analysis Results

### Highest Spending Customers
```sql
SELECT o.customer_id, c.name, SUM(o.total_amount) AS total_spent
FROM Orders o
JOIN Customers c
ON o.customer_id = c.customer_id
GROUP BY o.customer_id, c.name
ORDER BY total_spent DESC
LIMIT 5;
```
<img width="392" height="175" alt="Highest spending customer" src="https://github.com/user-attachments/assets/bf6723a1-a2ea-4805-9ce5-10817e317994" />

### Available genre
```sql
SELECT DISTINCT(genre)
FROM Books;
```
<img width="205" height="223" alt="available_genre" src="https://github.com/user-attachments/assets/a0be86ee-c7d5-437e-adf4-22b24ac8be5a" />


### 5 Most Expensive Books
```sql
SELECT *
FROM BOOKS
ORDER BY price DESC
LIMIT 5;
```

<img width="955" height="167" alt="5 most expensive books" src="https://github.com/user-attachments/assets/1edb2fcd-a9bb-44d7-8a89-043dfe914a34" />

### Book sold by each Genre
```sql
SELECT b.genre, SUM(o.quantity) AS total_books_sold
FROM Books b
INNER JOIN Orders o
ON b.book_id = o.book_id
GROUP BY b.genre;
```
<img width="315" height="217" alt="image" src="https://github.com/user-attachments/assets/4e8981bd-c67a-4636-aec6-54793e32e34b" />

### 5 Most Frequently Order Books
```sql
SELECT o.book_id, b.title, COUNT(o.order_id) AS order
FROM orders o
JOIN books b
ON o.book_id = b.book_id
GROUP BY o.book_id, b.title
ORDER BY COUNT(o.order_id) DESC LIMIT 1;
```
<img width="429" height="169" alt="most frequently order book" src="https://github.com/user-attachments/assets/6ed237bf-970b-404e-8754-b7d1b5d5c0e9" />

---

## 📊 SQL Concepts Covered

- DDL (CREATE, ALTER, DROP)
- DML (INSERT, UPDATE, DELETE)
- DQL (SELECT, WHERE, ORDER BY, LIMIT)
- Aggregate Functions (COUNT, SUM, AVG, MAX, MIN)
- Joins (INNER JOIN, LEFT JOIN)
- GROUP BY & HAVING
- Date Functions (EXTRACT)
- COALESCE and CASE

---

## 📈 SQL Queries Implemented

### Basic Queries

- Retrieve books by genre
- Calculate total stock
- Find the most expensive book
- Calculate total revenue, etc.

### Advanced Queries

- Best-selling books
- Books sold by genre
- Highest spending customer
- Remaining stock after sales
- Most expensive books

---

## Author
Erum Mansoori
- LinkedIn: [Erum Mansoori](https://www.linkedin.com/in/erum-mansoori/)
  
