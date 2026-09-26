# 🗄️ SQL Scripts

This folder contains all SQL scripts for the FoodHub Database System, organized in execution order.

## Contents

| File | Type | Description |
|------|------|-------------|
| `01-create-tables.sql` | DDL | Creates all tables with primary keys, foreign keys, and constraints |
| `02-insert-sample-data.sql` | DML | Inserts sample data for testing and demonstration |
| `03-queries.sql` | DML | Contains SELECT queries using WHERE, BETWEEN, IN, GROUP BY, HAVING, ORDER BY |
| `04-security-setup.sql` | DCL | Creates user groups, logins, and access permissions |

## Execution Order

Run the scripts in this exact order:

1. `01-create-tables.sql`
2. `02-insert-sample-data.sql`
3. `03-queries.sql`
4. `04-security-setup.sql`

## Database Details

- **DBMS:** Microsoft SQL Server
- **Database Name:** `FoodHubDB`
- **Tool:** SQL Server Management Studio (SSMS)

## Notes

- All scripts include comments explaining each statement
- Data validation is applied using CHECK constraints and foreign keys
- The database is normalized to Third Normal Form (3NF)
