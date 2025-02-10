# AdvancedatabasesHW2
# Entity-Relation Models

## Team Members
- **Rohith Nagapuri**
- **Charan Rao Thoodi**
- **Roshan Nagapuri**

## Table of Contents
1. [Introduction](#introduction)
2. [Library Management System](#library-management-system)
    - Problem Description
    - Chen Notation
    - Crow's Foot Notation
    - Relation Set Schema
    - Design Decisions
3. [School Course Enrollment System](#school-course-enrollment-system)
    - Problem Description
    - Chen Notation
    - Crow's Foot Notation
    - Relation Set Schema
    - Design Decisions
4. [Hotel Booking System](#hotel-booking-system)
    - Problem Description
    - Chen Notation
    - Crow's Foot Notation
    - Relation Set Schema
    - Design Decisions
5. [Conclusion](#conclusion)

---

## Introduction

Entity-Relation (ER) diagrams are fundamental in database design, representing real-world systems in structured data models. This report includes detailed ER diagrams and schemas for three systems:

1. **Library Management System**
2. **School Course Enrollment System**
3. **Hotel Booking System**

Each system is modeled using **Chen Notation** and **Crow's Foot Notation**, followed by a detailed relational schema and design discussions.

---

## Library Management System

### Problem Description
The Library Management System manages books, members, and loans:
- **Entities**:
  - `Book`: `book_id` (PK), `title`, `author`
  - `Member`: `member_id` (PK), `name`, `membership_date`
  - `Loan`: `loan_id` (PK), `loan_date`, `return_date`
- **Relationships**:
  - A **Member** can borrow multiple **Books**.
  - A **Book** can be borrowed by multiple **Members**.
  - Each **Loan** involves one **Member** and one **Book**.

### Chen Notation
![image alt](https://github.com/RohithNagapuri/AdvancedatabasesHW2/blob/c4b1c2dbb80096ee7fc718772bdf26f24e337929/Screenshot%202025-02-10%20011717db.png)
