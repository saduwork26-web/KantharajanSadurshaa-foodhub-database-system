# 🍔 FoodHub Database System

A complete relational database system designed for **FoodHub**, a fast-food delivery company expanding from the USA to Sri Lanka. This project covers the full database development lifecycle — from requirements gathering and ER modelling to normalization, SQL implementation, a working CRUD interface, security mechanisms, and testing.

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Business Scenario](#-business-scenario)
- [Objectives](#-objectives)
- [CRUD Operations](#-crud-operations)
- [Technologies Used](#️-technologies-used)
- [Database Design](#-database-design)
- [Repository Structure](#-repository-structure)
- [Getting Started](#-getting-started)
- [Sample Queries](#-sample-queries)
- [Security Implementation](#-security-implementation)
- [Testing](#-testing)
- [Project Status](#-project-status)
- [Connect](#-connect)

---

## 📌 Project Overview

FoodHub is a well-known fast-food delivery company based in the United States. After 14 years of success, the company is expanding globally and opening a new branch in Sri Lanka. This project delivers a **Database Management System (DBMS)** to support the delivery operations of the new branch.

The system is designed with **accuracy** and **consistency** at its core, ensuring data integrity throughout the data lifecycle. It manages:

- 👤 **Customer** information and delivery addresses
- 📦 **Order** details, statuses, and payment methods
- 🍕 **Food items**, categories, and ingredients
- 🏍️ **Riders** (delivery staff) and their dependents
- 🛵 **Motorbike** assignments and meter readings

---

## 🏢 Business Scenario

FoodHub delivers food to customers through dedicated delivery staff known as **Riders**. In the initial phase, the system focuses on **delivery management** only. Future enhancements will integrate **Human Resource Management** and **Finance Management** modules.

### Key Business Rules

| Rule | Description |
|------|-------------|
| **Customer** | Identified by unique Customer ID; can place many orders |
| **Orders** | Identified by unique Order No; placed via phone by a staff member |
| **Food Items** | Identified by Item Number; made with a minimum of 3 ingredients |
| **Riders** | Identified by Employee Number; can have multiple dependents |
| **Motorbikes** | Identified by unique registration number; assigned to riders per shift |
| **Dispatch** | Dispatch time is recorded when an order leaves the outlet |
| **Meter Readings** | Recorded when a bike is assigned and returned |

---

## 🎯 Objectives

- ✅ Identify user and system requirements for FoodHub
- ✅ Design a relational database using ER modelling (conceptual design)
- ✅ Convert the ER model to a logical schema with primary and foreign keys
- ✅ Normalize the database to 3NF to eliminate anomalies
- ✅ Implement SQL DDL and DML with proper data validation
- ✅ Build a **CRUD interface** for Insert, Update, Search, and Delete operations
- ✅ Apply security mechanisms (user groups, access permissions)
- ✅ Test the system against user and system requirements
- ✅ Produce technical and user documentation

---

## 🔄 CRUD Operations

The application provides a complete user interface for managing all database records.

| Operation | Feature | Screen |
|-----------|---------|--------|
| **Insert** | Register new customers, add food items, create orders, assign riders | `frmInsert` |
| **Update** | Modify order status, update rider details, edit item prices, record dispatch time | `frmUpdate` |
| **Search** | Find orders by customer, filter items by category, track riders by shift | `frmSearch` |
| **Delete** | Cancel orders, remove discontinued items, delete rider records | `frmDelete` |

---

## 🛠️ Technologies Used

| Category | Technology | Purpose |
|----------|-----------|---------|
| **Database** | Microsoft SQL Server | Database implementation |
| **DBMS Tool** | SQL Server Management Studio (SSMS) | Query execution, management, security |
| **Application** | C#.NET (Windows Forms) | CRUD user interface |
| **IDE** | Visual Studio | Application development |
| **Design** | draw.io / Lucidchart | ER diagram, schema design, flowcharts |
| **Documentation** | Markdown | Project documentation |
| **Version Control** | Git & GitHub | Source control and collaboration |

---

## 🗄️ Database Design

### Conceptual Design (ER Model)

The ER model captures all entities, attributes, relationships, cardinalities, and participation constraints.

**Entities:**
- Customer
- Order
- OrderItem
- FoodItem
- Ingredient
- ItemIngredient
- Rider
- Dependent
- Motorbike
- BikeAssignment

📎 *See [`docs/er-diagram.png`](docs/er-diagram.png) for the full ER diagram.*

### Logical Design

The logical schema includes:

- **Primary Keys** for all entities
- **Foreign Keys** establishing referential integrity
- **Composite Keys** for junction tables (e.g., OrderItem, ItemIngredient)
- **Surrogate Keys** for dependents (since they lack a natural unique identifier)

📎 *See [`docs/logical-design.md`](docs/logical-design.md) for the full schema.*

### Normalization

The database has been normalized through:

- **1NF** — Eliminated repeating groups (e.g., ingredients split into separate table)
- **2NF** — Removed partial dependencies (e.g., OrderItem has its own table)
- **3NF** — Removed transitive dependencies (e.g., ItemCategory separated)

📎 *See [`docs/normalization-report.md`](docs/normalization-report.md) for detailed proof.*

### Data Dictionary

A complete data dictionary documents every table, column, data type, constraint, and description.

📎 *See [`docs/data-dictionary.md`](docs/data-dictionary.md).*

---

## 📁 Repository Structure
