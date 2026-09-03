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
---
---
#### **ER Diagram: Types of Entities & Attributes**
* **Entity** → Strong / Weak
* **Attribute** → Simple / Composite / Multivalued / Derived / Complex
---
1. Entity Types
    1. **Strong Entity**
        * An entity whose existence does not depend on the existence of another entity.
        * A strong entity is identified by a **primary key** and is represented by a **single rectangle** in an ERD.
    2. **Weak Entity**
        * An entity whose existence depends on the existence of another entity, called the parent entity.
        * A weak entity is identified by a **partial key** and is connected to its parent entity through a **relationship**.
        * A weak entity is represented by a **double rectangle** in an ERD, and its relationship with the parent entity is represented by a **double diamond**, and this relationship is called an **identifying relationship**.
---
2. Attribute Types
    1. **Simple Attribute**
        * An attribute that cannot be divided into smaller subparts.
        * Represented by a **single oval** in an ERD.
    2. **Composite Attribute**
        * An attribute that can be divided into smaller subparts, which represent more basic attributes with independent meanings.
        * Represented by a **single oval** connected to multiple ovals in an ERD.
    3. **Multivalued Attribute**
        * An attribute that can have multiple values for a single entity instance.
        * Represented by a **double oval** in an ERD.
    4. **Derived Attribute**
        * An attribute whose value can be derived from other attributes in the database.
        * Represented by a **dashed oval** in an ERD.
    5. **Complex Attribute**
        * An attribute that is a combination of composite + multivalued
        * Represented by a **double oval** connected to multiple ovals in an ERD. 
---
* 🔵 **Properties of a Relationship**  
    1. **Degree of Relationship** :
        * The number of ***entities*** involved in a relationship.
        * **Unary** : Involves one entity type (e.g., Employee supervises Employee).
        * **Binary** : Involves two entity types (e.g., Student enrolls in Course).
        * **Ternary** : Involves three entity types (e.g., Supplier supplies Product to Store).
    2. **Participation Constraint** :
        * The minimum and maximum number of times an entity can participate in a relationship, in a simple word, are all rows of an entity must participate in the relationship or not.
        * **Total Participation** : An entity must participate in the relationship (all rows of the entity must participate in the relationship).
        * **Partial Participation** : An entity may or may not participate in the relationship (not all rows of the entity need to participate in the relationship).
    3. **Cardinality** :
        * The number of instances of one entity that can be associated with instances of another entity.
        * **One-to-One** : One instance of Entity A is associated with exactly one instance of Entity B.
        * **One-to-Many** : One instance of Entity A is associated with zero or many instances of Entity B.
        * **Many-to-Many** : Many instances of Entity A are associated with zero or many instances of Entity B.
---
🔑 **Types of Keys**
1. **Key** : A set of attributes that uniquely identifies an instance of an entity.
    1. **Candidate Key** : A ***minimal set*** of attributes that can uniquely identify an instance of an entity.
        * minimal means that if we remove any attribute from the set, it will no longer uniquely identify the instance. 
    2. **Alternate Key** : A candidate key that is not selected as the primary key.
    3. **Primary Key** : A candidate key that is selected as the main identifier for the entity.
    4. **Composite Key** : A key that consists of two or more attributes that together uniquely identify an instance of an entity.
    5. **Foreign Key** : A field in one table that references the primary key of another table, used to establish relationships between tables.
    6. **Super Key** : A set of attributes that uniquely identifies an instance of an entity, it may contain more attributes than necessary to uniquely identify the instance (i.e., it may not be minimal, so it contains extra attributes), we can consider it as a general case.
    7. **Partial Key** : A set of attributes that uniquely identifies a weak entity, it is used in conjunction with the primary key of the parent entity to form a composite key for the weak entity.


    * **Example** : (minimal unique cols)
        * ID  (Candidate key) (PK)
        * Phone  (Candidate key) (Alternative key)
        * Nationality_ID (Candidate key) (Alternative key)
            * All of them considered as Candidate keys(also considered as Super keys) 
            * If we chose ID to be a PK, the rest of cols considered as alternative keys.