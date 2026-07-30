# 📚 Library Management System

A **Library Management System** built using **MySQL** to manage books, students, and book issue/return operations. The project demonstrates relational database design, data integrity using foreign keys, and automation using SQL triggers.

---

## 📖 Project Overview

This project is designed to simplify library operations by maintaining records of:

- Books
- Students
- Book Issue & Return Transactions

The database automatically updates book availability and prevents issuing unavailable books using MySQL triggers.

---

## 🚀 Features

- 📚 Manage book records
- 👨‍🎓 Manage student records
- 🔄 Issue and return books
- 🔑 Primary & Foreign Key relationships
- ⚡ Automatic book quantity updates using Triggers
- ✅ Prevent issuing books when stock is unavailable
- 💾 Sample data included for testing

---

# 🛠 Technologies Used

- MySQL
- MySQL Workbench
- SQL

---

# 🗂 Database Schema

## Tables

### 📘 Books

Stores book information.

| Column | Data Type |
|---------|-----------|
| book_id | INT (Primary Key) |
| title | VARCHAR(100) |
| author | VARCHAR(100) |
| quantity | INT |

---

### 👨‍🎓 Students

Stores student details.

| Column | Data Type |
|---------|-----------|
| student_id | INT (Primary Key) |
| student_name | VARCHAR(100) |
| department | VARCHAR(50) |

---

### 📋 Issued Books

Stores issued book transactions.

| Column | Data Type |
|---------|-----------|
| issue_id | INT (Primary Key) |
| book_id | INT (Foreign Key) |
| student_id | INT (Foreign Key) |
| issue_date | DATE |
| return_date | DATE |

---

# 🔗 Relationships

- Books → Issued Books (One-to-Many)
- Students → Issued Books (One-to-Many)

Foreign Keys ensure data consistency and prevent invalid records.

---

# ⚡ Triggers Implemented

## 1. check_quantity (BEFORE INSERT)

Checks book availability before issuing a book.

**Purpose**

- Prevents issuing books when quantity is zero.
- Displays the message:

```
Book Not Available
```

---

## 2. reduce_quantity (AFTER INSERT)

Automatically decreases the book quantity after a successful issue.

Example:

```
Before Issue : 10
After Issue  : 9
```

---

## 3. increase_quantity (AFTER UPDATE)

Automatically increases the quantity when a returned book's `return_date` is updated.

Example:

```
Before Return : 9
After Return  : 10
```

---

# 📂 Project Structure

```
Library-Management-System/
│
├── library_management.sql
├── README.md
```

---

# 💻 How to Run

## 1. Clone the repository

```bash
git clone https://github.com/yourusername/Library-Management-System.git
```

---

## 2. Open MySQL Workbench

Go to:

```
Server → Data Import
```

---

## 3. Select

```
Import from Self-Contained File
```

Choose

```
library_management.sql
```

Click

```
Start Import
```

---

## 4. Use the Database

```sql
USE library_management;
```

---

# 🧪 Sample Queries

```sql
SELECT * FROM books;
```

```sql
SELECT * FROM students;
```

```sql
SELECT * FROM issued_books;
```

---

# 📈 Learning Outcomes

Through this project, I gained hands-on experience in:

- Relational Database Design
- SQL Constraints
- Primary & Foreign Keys
- CRUD Operations
- MySQL Triggers
- Data Integrity
- Database Import & Export
- GitHub Project Management

---

# 👨‍💻 Author

**Siva Kumar Bathala**

📧 Email: shivakumar4p1@gmail.com

🔗 LinkedIn: https://www.linkedin.com/in/siva-kumar-721115327

---

## ⭐ If you found this project useful, consider giving it a star!
