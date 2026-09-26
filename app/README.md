# 💻 Application

This folder contains the C#.NET WinForms application that provides a **CRUD interface** for managing the FoodHub database.

## Purpose

The application gives staff members a user-friendly way to interact with the database without writing SQL directly. It supports the four core operations required by the system.

## CRUD Features

| Operation | Form | Description |
|-----------|------|-------------|
| **Insert** | `frmInsert` | Add new customers, riders, food items, and orders |
| **Update** | `frmUpdate` | Modify existing records (order status, rider details, prices) |
| **Search** | `frmSearch` | Retrieve records using filters (customer ID, order date, category) |
| **Delete** | `frmDelete` | Remove records with confirmation prompts |

## Folder Structure


## Technologies

- **Language:** C#.NET
- **Framework:** Windows Forms (.NET)
- **IDE:** Visual Studio 2022
- **Database:** Microsoft SQL Server
- **Data Access:** ADO.NET (SqlConnection, SqlCommand, SqlDataAdapter)

## Setup Instructions

1. Open `FoodHubApp.sln` in Visual Studio.
2. Update the connection string in `Database/Connection.cs` to match your SQL Server instance.
3. Build the solution (`Ctrl + Shift + B`).
4. Run the application (`F5`).

## Screenshots

See the ['screenshots'](screenshots) folder for evidence of each form in action.
