# 🎓 University Course Management System — SQL Assignment 1

A relational database project built in **SQL (PostgreSQL)** to manage students, courses, instructors, departments, and enrollments of a university. The assignment covers table design, CRUD operations, filtering, aggregation, joins, subqueries, string/date functions, window functions, and conditional logic.

---

## 📌 Project Overview

| Item | Details |
|------|---------|
| **Database** | `university_course_management1` |
| **SQL Dialect** | PostgreSQL |
| **Tables** | 5 (Departments, Students, Courses, Instructors, Enrollments) |
| **Queries** | 16 (including full CRUD on every table) |
| **Author** | Rajat Prajapati (RJ) |

---

## 🗂️ Database Schema

```
Departments (DepartmentID PK, DepartmentName)
     │
     ├──< Courses (CourseID PK, CourseName, DepartmentID FK, Credits)
     │         │
     │         └──< Enrollments (EnrollmentID PK, StudentID FK, CourseID FK, EnrollmentDate)
     │                                      │
     │                                      └── Students (StudentID PK, FirstName, LastName,
     │                                                    Email UNIQUE, BirthDate, EnrollmentDate)
     │
     └──< Instructors (InstructorID PK, FirstName, LastName, Email UNIQUE,
                       DepartmentID FK, Salary)
```

**Relationships**
- One **Department** → many **Courses** and many **Instructors**
- **Students** ↔ **Courses** is many-to-many, resolved through **Enrollments**

---

## 📊 Sample Data

| Table | Rows |
|-------|------|
| Departments | 4 |
| Students | 12 |
| Courses | 6 |
| Instructors | 4 |
| Enrollments | 24 |

---

## ❓ Questions Covered

| # | Task | Concept |
|---|------|---------|
| 1 | Create, Read, Update, Delete on all 5 tables | CRUD (`INSERT`, `SELECT`, `UPDATE`, `DELETE`) |
| 2 | Students enrolled after 2022 | `WHERE` with date filter |
| 3 | Up to 5 courses of the Mathematics department | `JOIN` + `LIMIT` |
| 4 | Courses with more than 5 students | `GROUP BY` + `HAVING` |
| 5 | Students enrolled in **both** Intro to SQL and Data Structures | `HAVING COUNT(DISTINCT ...)` |
| 6 | Students enrolled in **either** of the two courses | `IN` + `DISTINCT` |
| 7 | Average credits of all courses | `AVG()` |
| 8 | Maximum salary in Computer Science | `MAX()` + `JOIN` |
| 9 | Students enrolled per department | Multi-table `JOIN` + `COUNT(DISTINCT)` |
| 10 | Students and their courses | `INNER JOIN` |
| 11 | All students and their courses, if any | `LEFT JOIN` |
| 12 | Students in courses with more than 10 students | Subquery |
| 13 | Extract year from `EnrollmentDate` | `EXTRACT()` |
| 14 | Concatenate instructor first + last name | `CONCAT()` |
| 15 | Running total of enrollments | Window function `COUNT() OVER (ORDER BY ...)` |
| 16 | Label students as Senior / Junior | `CASE WHEN` + date arithmetic |

---

## 🚀 How to Run

1. Install **PostgreSQL** and open **pgAdmin** or `psql`.
2. Create the database:
   ```sql
   CREATE DATABASE university_course_management1;
   ```
3. Connect to `university_course_management1`.
4. Open `assignment-1-sql-rajat.sql` and run the remaining script (tables → inserts → queries).

> 💡 Run the script top to bottom — tables must exist before data is inserted, and parent tables (Departments, Students, Courses) must be created before Enrollments because of foreign keys.

---

## 🧠 Key Concepts Practiced

- Primary keys, foreign keys, `UNIQUE` and `NOT NULL` constraints
- Data types: `INT`, `VARCHAR`, `DATE`, `NUMERIC`
- Filtering and sorting data
- Aggregate functions with `GROUP BY` and `HAVING`
- `INNER JOIN` vs `LEFT JOIN`
- Subqueries
- String, date, and window functions
- Conditional logic with `CASE`

---

## 📁 Repository Structure

```
├── assignment-1-sql-rajat.sql   # Full script: schema, data, and all 16 queries
└── README.md                    # Project documentation
```

---

## 👤 Author

**Rajat Prajapati**
