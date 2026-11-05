# Logical Database Design

This document takes the conceptual ER diagram and turns it into a logical relational schema. It defines the tables, the PKS, the FKS and the data types needed to actually build the database in SQL Server.

1.  **Customer Table**

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Customer_ID | INT | Primary Key | To identify the customer uniquely. |
| NIC | VARCHAR (12) | Candidate Key | National Identity Card number |
| DOB | DATE |     | Date of Birth |
| Contact_Number | VARCHAR (10) |     | Phone Number |
| Location_No | INT |     | Address Line 1 |
| Lane | VARCHAR (50) |     | Address Line 2 |
| Street | VARCHAR (50) |     | Address Line 3 |
| City | VARCHAR (50) |     | City |

**Description:** Stores the details of the customers who are placing orders.

2.  **Staff Table**

**Description:** Stores the details of the staff members who enter the orders.

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Staff_ID | INT | Primary Key | To identify the staff members uniquely. |
| NIC | VARCHAR (12) | Candidate Key | National Identity Card number |
| First_Name | VARCHAR (50) |     | First name of the staff members |
| Last_Name | VARCHAR (50) |     | Last name of the staff members |
| Staff_Address | VARCHAR (200) |     | Address of the staff members |
| Contact_Number | VARCHAR (10) |     | Phone Number |

3.  **Order Table**

**Description:** Stores the details of the orders placed.

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Order_No | INT | Primary Key | To identify the orders uniquely |
| Order_Date | DATE |     | The date when the order was placed |
| Order_Time | TIME |     | The time when the order was placed |
| Order_Status | VARCHAR (20) |     | Whether the order was successfully delivered or not |
| Payment_Method | VARCHAR (20) |     | Whether the payment method is cash on delivery or card payment |
| Dispatch_Time | TIME |     | The time when the order is dispatched from the Kitchen |
| Customer_ID | INT | Foreign Key | Primary key of Customer table |
| Staff_ID | INT | Foreign Key | Primary key of Staff table |
| Employee_Number | INT | Foreign Key | Primary key of Rider table |

4.  **Item Table**

**Description:** Stores the details of the ordered items.

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Item_Number | INT | Primary Key | To identify the items uniquely |
| Item_Name | VARCHAR (20) |     | Name of the item |
| Item_Category | VARCHAR (20) |     | The category of the item |
| Price | DECIMAL (10, 2) |     | Price of the item |

5.  **Ordered_Item Table**

**Description:** Resolves the Many-to-Many relationship between Order and Item.

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Order_No | INT | Foreign Key | Primary key of Order table |
| Item_Number | INT | Foreign Key | Primary key of Item table |
| Quantity | INT |     | Quantity of the ordered item |

6.  **Ingredient Table**

**Description:** Resolves the multivalued attribute Ingredient from Items.

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Item_Number | INT | Composite Primary Key | Primary key of Item table |
| Ingredient_Name | VARCHAR (20) | Composite Primary Key | Name of the ingredients in ordered items |

7.  **Rider Table**

**Description:** Stores the details of the riders who are delivering the orders.

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Employee_Number | INT | Primary Key | To identify the riders uniquely |
| NIC | VARCHAR (12) | Candidate Key | National Identity Card number |
| DOB | DATE |     | Date of Birth |
| First_Name | VARCHAR (50) |     | First name of the rider |
| Middle_Name | VARCHAR (50) |     | Middle name of the rider |
| Last_Name | VARCHAR (50) |     | Last name of the rider |
| Rider_Address | VARCHAR (200) |     | Address of the rider |
| Contact_Number | VARCHAR (10) |     | Phone number |
| License_Number | VARCHAR (50) |     | License number of the rider |

8.  **Dependent Table**

**Description:** Stores the details of the dependents of the riders.

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Employee_Number | INT | Foreign Key | Primary key of Rider table |
| Dependent_Name | VARCHAR (50) | Composite Primary Key | To identify the dependent |
| DOB | DATE |     | Date of Birth |
| Relationship_to_the_rider | VARCHAR (50) |     | What is the relationship between riders and dependents |

9.  **Motorbike Table**

**Description:** Stores the details of the motorbikes.

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Vehicle_Registration_Number | VARCHAR (20) | Primary Key | To identify the motorbike uniquely |
| Vehicle_Registered_Date | DATE |     | The date when the motorbike was registered |
| Brand | VARCHAR (50) |     | The brand name of the motorbike |
| Model | VARCHAR (50) |     | The model’s name of the motorbike |
| Engine_Number | VARCHAR (20) |     | The engine number of the motorbike |

10.  **Motorbike_Color Table**

**Description:** Resolves the multivalued attribute Color from Motorbike.

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Vehicle_Registration_Number | VARCHAR (20) | Foreign Key | Primary key of Motorbike table |
| Color | VARCHAR (10) | Composite Primary Key | The color of the motorbike |

11.  **Bike_Assignment Table**

**Description:** Resolves the Many-to-Many relationship between Rider and Motorbike.

| **Column Name** | **Data Type** | **Key** | **Description** |
| --------------- | ------------- | ------- | --------------- |
| Assignment_ID | INT | Primary Key | To identify the bike assignment uniquely |
| Employee_Number | INT | Foreign Key | Primary key of Rider table |
| Vehicle_Registration_Number | VARCHAR (20) | Foreign Key | Primary key of Motorbike table |
| Date_Used | DATE |     | The date when the bike was used for delivery |
| Shift | VARCHAR (10) |     | The shift of the rider; whether it is daytime or nighttime |
| Meter_Reading_When_Assigned | INT |     | The meter reading of the bike when it was assigned for the delivery |
| Meter_Reading_When_Returned | INT |     | The meter reading of the bike when it was returned after the delivery |

## Normalization Report – FoodHub Database System

As (Coronel, 2018) point out, normalization is the process of organizing the data in such a way as to minimize redundancy and remove the possibility of anomalies. The FoodHub database has been normalized through the following stages:

### First Normal Form (1NF)

A table is in 1NF if it contains only atomic (indivisible) values and there are no repeating groups.

**Justification:** In the initial design, a food item could have multiple ingredients, and a motorbike could have multiple colors. To achieve 1NF, these multivalued attributes were removed from the main \`Item\` and \`Motorbike\` tables. They were placed into their own separate tables: \`Ingredient\` and \`Motorbike_Color\`. Additionally, the \`Ordered_Item\` table was created to handle the multiple items within a single order, ensuring every column holds only one value per row.

### Second Normal Form (2NF)

A table is in 2NF if it is in 1NF and all non-key attributes are fully functionally dependent on the primary key (no partial dependencies).

**Justification:** This rule applies mostly to our tables with Composite Primary Keys. For example, in the \`Ordered_Item\` table, the primary key is a combination of \`Order_No\` and \`Item_Number\`. The attribute \`Quantity\` depends on both the order and the item. Therefore, there are no partial dependencies. The same applies to the \`Ingredient\` and \`Motorbike_Color\` tables.

### Third Normal Form (3NF)

A table is in 3NF if it is in 2NF and there are no transitive dependencies (where a non-key attribute depends on another non-key attribute).

**Justification:** The data for all 11 tables has been broken down into separate entities, so that attributes only depend on their respective primary keys and keep all 11 tables in 3NF:

- Customer, Staff, Rider and Motorbike Tables: Non-key attributes (such as Name, Address, DOB, and Contact_Number) depend only on their primary key. There's no Order table, only the Customer table where the customers' address is stored.

- Order Table: The attributes (Order_Date, Order_Time, Order_Status, Payment_Method, and Dispatch_Time) are dependent on the Order_No. Foreign keys Customer_ID and Employee_Number are used to avoid the transitive dependency.

- Item Table: Item_Name, Category and Price are dependent on only the Item_Number.
- Dependent Table: The composite key (Employee_Number + Dependent_Name) depends only on the attributes DOB and Relationship_to_the_rider.

- Bike_Assignment Table: The attributes (Meter_Reading_When_Assigned, Meter_Reading_When_Returned, Date_Used, and Shift). Therefore, there is no transitive dependency on Rider or Motorbike.

- Association tables (Ordered_Item, Ingredient, Motorbike_Color): These tables have only Foreign Keys and a single descriptive attribute and are therefore it is in 3NF.

Conclusion:

The FoodHub database design not only satisfies these requirements for Third Normal Form (3NF), but they also ensure that there are no data anomalies in the system.

# References

Coronel, C., 2018. _Database Systems: Design, Implementation, and Management._ 13th edn ed. Boston: engage Learning.
