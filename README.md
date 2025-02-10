# ADVANCED DATABASE HW2
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

### Chen Notation(graphviz)
![image alt](https://github.com/RohithNagapuri/AdvancedatabasesHW2/blob/c4b1c2dbb80096ee7fc718772bdf26f24e337929/Screenshot%202025-02-10%20011717db.png)

### Crows Foot Notation(mermaid)
![image alt](https://github.com/RohithNagapuri/AdvancedatabasesHW2/blob/07aae8a56ae358cfbfb6f441966a6e07eb6f1b6c/mermaid-ai-diagram-2025-02-10-055014.png)

### Relation Set Schema

- **Book**(`book_id` PK, `title`, `author`)
- **Member**(`member_id` PK, `name`, `membership_date`)
- **Loan**(`loan_id` PK, `loan_date`, `return_date`, `member_id` FK, `book_id` FK)

---

### Design Decisions

- **Cardinality and Participation**: Appropriate cardinality and participation constraints are defined in the Crow's Foot diagrams for all systems:
  - **Library Management System**: A member can borrow multiple books (optional participation for books and members in loans).
  - **School Course Enrollment System**: A student can enroll in multiple courses (mandatory participation for enrollments).
  - **Hotel Booking System**: A guest can make multiple bookings (optional participation for rooms and guests in bookings).
  
- **Weak Entities**: 
  - No weak entities were introduced as all entities have unique primary keys.
  
- **Composite Attributes**:
  - Composite attributes like "name" were simplified into single attributes for ease of querying.
  
- **Multivalued Attributes**:
  - Multivalued attributes were avoided by introducing separate entities or bridge tables to handle many-to-many relationships.

---

## School Course Enrollment System

### Problem Description

The School Course Enrollment System manages courses, students, and enrollments:

- **Entities**:
  - **Course**: `course_id` (PK), `title`, `credits`
  - **Student**: `student_id` (PK), `name`, `enrollment_date`
  - **Enrollment**: `enrollment_id` (PK), `enrollment_date`, `grade`

- **Relationships**:
  - A **Student** can enroll in multiple **Courses**.
  - A **Course** can have multiple **Students**.
  - Each **Enrollment** involves one **Student** and one **Course**.

### Chen Notation(graphviz)
![image alt](https://github.com/RohithNagapuri/AdvancedatabasesHW2/blob/07aae8a56ae358cfbfb6f441966a6e07eb6f1b6c/Screenshot%202025-02-10%20012709db2.png)
### Crows Foot Notation(mermaid)
![image alt](https://github.com/RohithNagapuri/AdvancedatabasesHW2/blob/07aae8a56ae358cfbfb6f441966a6e07eb6f1b6c/Untitled%20diagram-2025-02-10-060955.png)

### Design Choices

- **Weak Entities**: 
  - Enrollment is treated as a regular entity to capture additional attributes like `grade`.

- **Composite Attributes**: 
  - None were used.

- **Multivalued Attributes**: 
  - None were introduced.

- **Cardinality**: 
  - A student can enroll in multiple courses, and each course can have multiple students.

- **Participation**: 
  - Total participation of **Enrollment** with both **Student** and **Course** entities.

---

### Relational Set Schemas

- **Student**(`student_id` PK, `name`, `enrollment_date`)
- **Course**(`course_id` PK, `title`, `credits`)
- **Enrollment**(`enrollment_id` PK, `enrollment_date`, `grade`, `student_id` FK, `course_id` FK)

---

## Hotel Booking System

### Problem Description

The Hotel Booking System tracks rooms, guests, and bookings:

- **Entities**:
  - **Room**: `room_number` (PK), `type`, `rate`
  - **Guest**: `guest_id` (PK), `name`, `contact_information`
  - **Booking**: `booking_id` (PK), `check_in_date`, `check_out_date`

- **Relationships**:
  - A **Guest** can make multiple **Bookings**.
  - A **Room** can have multiple **Bookings**.
  - Each **Booking** involves one **Guest** and one **Room**.

### Chen Notation(graphviz)
![image alt](https://github.com/RohithNagapuri/AdvancedatabasesHW2/blob/07aae8a56ae358cfbfb6f441966a6e07eb6f1b6c/Screenshot%202025-02-10%20012806db3.png)

### Crows Foot Notation(mermaid)
![image alt](https://github.com/RohithNagapuri/AdvancedatabasesHW2/blob/07aae8a56ae358cfbfb6f441966a6e07eb6f1b6c/mermaid-ai-diagram-2025-02-10-062355.png)

### Design Choices

- **Weak Entities**: 
  - None were introduced.

- **Composite Attributes**: 
  - `ContactInfo` could be composite but was kept as a single attribute for simplicity.

- **Multivalued Attributes**: 
  - None were introduced.

- **Cardinality**: 
  - A guest can make multiple bookings, and each room can be booked multiple times.

- **Participation**: 
  - Total participation of **Booking** with both **Guest** and **Room** entities.

---

### Relational Set Schemas

- **Guest**(`guest_id` PK, `name`, `contact_information`)
- **Room**(`room_number` PK, `type`, `rate`)
- **Booking**(`booking_id` PK, `check_in_date`, `check_out_date`, `guest_id` FK, `room_number` FK)

---

## Conclusion

The ER diagrams for the **Library Management System**, **School Course Enrollment System**, and **Hotel Booking System** effectively model their respective databases. The design decisions prioritize scalability, normalization, and ease of querying while balancing tradeoffs like performance and complexity.

Each system provides a solid foundation for implementation and supports future enhancements. These designs emphasize flexibility and maintainability, making them suitable for real-world database applications.
