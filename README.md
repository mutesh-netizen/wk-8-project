# wk-8-project
# Library Management System Database

## Project Overview

This project implements a **relational database schema** for a Library Management System using MySQL.  
It models authors, books, library members, and book loans to efficiently manage library operations.

---

## Database Design

The schema includes the following tables with appropriate keys and relationships:

| Table    | Description                              | Key Constraints                         |
|----------|----------------------------------------|---------------------------------------|
| Authors  | Stores author details                   | `AuthorID` (PK)                       |
| Books    | Stores book information                 | `BookID` (PK), `AuthorID` (FK)       |
| Members  | Stores library member details           | `MemberID` (PK), `Email` UNIQUE       |
| Loans    | Tracks book loans to members            | `LoanID` (PK), `BookID` (FK), `MemberID` (FK) |

---

## Features

- One-to-many relationship between **Authors** and **Books**
- Many-to-many relationship between **Books** and **Members** via the **Loans** table
- Proper use of primary keys, foreign keys, and unique constraints to maintain data integrity
- Supports tracking of loan and return dates

---

## Setup Instructions

1. **Install MySQL** if not already installed.  
2. Open MySQL Workbench or your preferred MySQL client.  
3. Create and use the database by running the script:

```sql
-- Run the full SQL script from `library_management.sql`
SOURCE path/to/library_management.sql;

Optionally, insert sample data for testing:

INSERT INTO Authors (Name) VALUES ('J.K. Rowling'), ('George Orwell'), ('Jane Austen');

INSERT INTO Books (Title, ISBN, AuthorID) VALUES
('Harry Potter and the Sorcerer''s Stone', '9780439554930', 1),
('1984', '9780451524935', 2),
('Pride and Prejudice', '9781503290563', 3);

INSERT INTO Members (Name, Email) VALUES
('Alice Johnson', 'alice@example.com'),
('Bob Smith', 'bob@example.com');

INSERT INTO Loans (BookID, MemberID, LoanDate) VALUES
(1, 1, '2025-09-01'),
(2, 2, '2025-09-05');

Usage

Query the database to retrieve author, book, member, and loan information.

Extend the schema as needed for additional features (e.g., categories, publishers).

File Description

library_management.sql — Contains all CREATE DATABASE and CREATE TABLE statements with constraints and relationships.

Contact

For any questions or issues, please contact:
newtonmutembei047@gmail.com

License

This project is for academic use only.
