# DB Life Cycle

## Overview

* Building a **database-driven system** goes through ***several stages***:

→ **Client Requirements**
→ **Analysis**
→ **Design**
→ **Mapping**
→ **Schema and tables**
→ **Implementation**
→ **End User**

---

### 1. **System Analyst**

* **The System Analyst** works with the client to understand the business requirements and define the project scope.

#### ***Main Output***
- Requirements Document

#### ***Main Responsibility***
Translate business requirements into clear system requirements.

---

### 2. **Database Designer**

* **The Database Designer** transforms the requirements into a **database design**.

#### ***Main Tasks***
- **Identify Entities** : **Entity** ≠ Table, An **Entity** represents **an important object/component** in the system that **we need to store data about.**
- **Identify Attributes**
- **Identify Relationships**
- **Create ERD** : **ERD** = Entity Relationship Diagram, It represents: Entities, Attributes, Relationships, it is a **graphical representation** of the database design not the actual/physical database.
- **Perform Database Mapping**

---

### 4. **Database Mapping**

* Database Mapping applies **predefined rules to an ERD** to **produce the relational schema and actual tables**.

#### ***Main Output***
- **Relational Schema**
- **Actual Tables**

##### **Client Requirements -> ERD -> Mapping -> Relational Schema -> Actual Tables**
---

### 5. **Database Developer**

* The Database Developer **implements the database** using an RDBMS and SQL.

### Examples of RDBMS (Relational Database Management System)
- SQL Server
- Oracle
- MySQL

### Important
**SQL** = Language (Structured Query Language)

**SQL Server** = RDBMS/Product (A tool that implements SQL)

---

### 6. **Application Developer**

* The **Application Developer** builds **the application/interface** that communicates with the database.

* The **End User** normally interacts with the application, **not directly with the database**.
---
* Notes : 
    1. **DB architecture in production could be** : Centralized - distributed DB - Replication - Sharding - Cloud DB - Multi-tenant DB.
    2. The same database can be used by multiple applications:
    3. The programming language used to build the application is not necessarily tied to the database vendor ex : SQL Server can be used with C#, Java, Python, etc, not just C#. 
---
### **Database Developer vs Application Programmer**

### 1. **Database Developer**
**Responsible for**: Database creation - Security - Performance - Queries

### Application Programmer
**Responsible for**: Building the application - GUI / Interface - Communicating with the database
---
### **Application Architecture***(A simplified architecture)*****
* The **End User** interacts with the **Application**, not directly with the Database, When the application needs data, it sends **SQL queries** to the **Database Server**.
* Database Server, **executes the query**, **returns data**, Application **displays the result** to the End User.
