# 🧪 Testing

This folder contains the test plan and test case results for the FoodHub Database System.

## Purpose

The testing documentation verifies that the system meets both **user requirements** and **system requirements** as identified during the analysis phase.

## Contents

| File | Description |
|------|-------------|
| `test-cases.md` | Detailed test cases with expected vs. actual results |

## Test Categories

| Category | What It Tests |
|----------|---------------|
| **Functional Testing** | CRUD operations (Insert, Update, Search, Delete) |
| **Data Validation** | CHECK constraints, NOT NULL, data types |
| **Referential Integrity** | Foreign key constraints and cascading behavior |
| **Security Testing** | User groups and access permissions |
| **Query Testing** | SELECT queries with WHERE, BETWEEN, IN, GROUP BY, HAVING, ORDER BY |

## Test Case Format

Each test case includes:

- **Test ID** — Unique identifier (e.g., TC-01)
- **Test Description** — What is being tested
- **Preconditions** — What must be true before testing
- **Test Steps** — Step-by-step actions
- **Expected Result** — What should happen
- **Actual Result** — What actually happened
- **Status** — Pass / Fail
- **Screenshots** — Visual evidence

## Example Test Case

| Field | Value |
|-------|-------|
| **Test ID** | TC-01 |
| **Description** | Insert a new customer into the database |
| **Preconditions** | Database is running; Insert form is open |
| **Test Steps** | 1. Enter valid customer details<br>2. Click "Insert" button |
| **Expected Result** | Customer record is added; confirmation message shown |
| **Actual Result** | *(to be filled during testing)* |
| **Status** | *(to be filled)* |

See [`test-cases.md`](test-cases.md) for the complete test plan.
