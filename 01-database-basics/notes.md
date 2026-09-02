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

### 2. **Application Programmer**

**Responsible for**: Building the application - GUI / Interface - Communicating with the database
---
### **Application Architecture(A simplified architecture)**
* The **End User** interacts with the **Application**, not directly with the Database, When the application needs data, it sends **SQL queries** to the **Database Server**.
* Database Server, **executes the query**, **returns data**, Application **displays the result** to the End User.
---
---
## **Database System Components**
1. **Database** : consists of **structured tables** connected through **relationships**.
2. **Database Management System (DBMS)** : A software that **manages the database** and provides an interface for users to interact with the database.
3. **Database Application** : A software that **interacts with the database** to perform specific tasks, such as data entry, retrieval, and reporting. 
---
## Data vs Metadata

### Data
* The actual values stored in the database.

### Metadata
* Data that describes the structure and organization of the data (Table names, Column names, Data types, Relationships, Primary keys, Foreign keys, Constraints), **ERD mainly represents metadata about the database structure.**
---
## **`Primary Key`**

* A primary key uniquely identifies each row in a table (Unique + NOT NULL = PK)
---
## **`Foreign Key`**

* A foreign key is used to establish a relationship between tables by referencing a key in another table, **Foreign keys help maintain referential integrity.**

---
## **`NULL`**

* **`NULL`** represents an **unknown** or **missing value**, NOT an empty string or zero. It indicates that the value is not applicable or not provided, So is SQL, we write **`where x IS NULL`**, not where x = NULL, because **`NULL`** **is not a value, it is a state of being unknown or missing.** 
---
## **`Constraints`**

* Constraints are rules enforced by the database on stored data (Primary Key, Foreign Key, Not Null, Unique, Check).
---
---
## **ER Diagram**

* An **Entity-Relationship Diagram** (ERD) is a **modeling technique** used **to transform system requirements into a visual model that describes the main components of a system and the relationships between them**.

* **The main components are:**
- **Entities** : represents an important object/concept in the system about which we need to store data (Drawn as Rectangel).
- **Attributes** : An attribute describes a characteristic/property of an entity (Drawn as Circle/Oval).
- **Relationships** : A relationship represents an association between entities (Drawn as Diamond).
---

### **Some important concepts**
* **Relationship Attributes**: Belong to the association between entities, not a single entity (e.g., Grade belongs to Student enrolls in Course).
    * **Identification Rule**: Ask what the attribute describes. If it describes an object → Entity Attribute. If it describes the link → Relationship Attribute.

* **Extracting ERD**: As a heuristic, **Nouns** = Entities/Attributes, and **Verbs** = Relationships.

* **Multiple Relationships**: Two entities can have multiple distinct relationships as long as the meanings differ (e.g., an Employee works for and manages a Department), but it have to be in diffrent meanings.

* **ERD vs. Schema**: ERD is a conceptual design. Do not confuse it with the final implementation phase (SQL tables and foreign keys).