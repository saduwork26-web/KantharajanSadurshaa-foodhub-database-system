# Data Dictionary

|     |     |     |     |     |
| --- | --- | --- | --- | --- |
| **Table Name** | **Column Name** | **Data Type** | **Key** | **Description** |
| **Customer** | Customer_ID | INT | Primary Key | To identify the customer uniquely. |
| NIC | VARCHAR (12) | Candidate Key | National Identity Card number |
| DOB | DATE |     | Date of Birth |
| Contact_Number | VARCHAR (10) |     | Phone Number |
| Location_No | INT |     | Address Line 1 |
| Lane | VARCHAR (50) |     | Address Line 2 |
| Street | VARCHAR (50) |     | Address Line 3 |
| City | VARCHAR (50) |     | City |
| **Staff** | Staff_ID | INT | Primary Key | To identify the staff members uniquely. |
| NIC | VARCHAR (12) | Candidate Key | National Identity Card number |
| First_Name | VARCHAR (50) |     | First name of the staff members |
| Last_Name | VARCHAR (50) |     | Last name of the staff members |
| Staff_Address | VARCHAR (200) |     | Address of the staff members |
| Contact_Number | VARCHAR (10) |     | Phone Number |
| **Order** | Order_No | INT | Primary Key | To identify the orders uniquely |
| Order_Date | DATE |     | The date when the order was placed |
| Order_Time | TIME |     | The time when the order was placed |
| Order_Status | VARCHAR (20) |     | Whether the order was successfully delivered or not |
| Payment_Method | VARCHAR (20) |     | Whether the payment method is cash on delivery or card payment |
| Dispatch_Time | TIME |     | The time when the order is dispatched from the Kitchen |
| Customer_ID | INT | Foreign Key | Primary key of Customer table |
| Staff_ID | INT | Foreign Key | Primary key of Staff table |
| Employee_Number | INT | Foreign Key | Primary key of Rider table |
| **Item** | Item_Number | INT | Primary Key | To identify the items uniquely |
| Item_Name | VARCHAR (20) |     | Name of the item |
| Item_Category | VARCHAR (20) |     | The category of the item |
| Price | DECIMAL (10, 2) |     | Price of the item |
| **Ordered_Item** | Order_No | INT | Foreign Key | Primary key of Order table |
| Item_Number | INT | Foreign Key | Primary key of Item table |
| Quantity | INT |     | Quantity of the ordered item |
| **Ingredient** | Item_Number | INT | Composite Primary Key | Primary key of Item table |
| Ingredient_Name | VARCHAR (20) | Composite Primary Key | Name of the ingredients in ordered items |
| **Rider** | Employee_Number | INT | Primary Key | To identify the riders uniquely |
| NIC | VARCHAR (12) | Candidate Key | National Identity Card number |
| DOB | DATE |     | Date of Birth |
| First_Name | VARCHAR (50) |     | First name of the rider |
| Middle_Name | VARCHAR (50) |     | Middle name of the rider |
| Last_Name | VARCHAR (50) |     | Last name of the rider |
| Rider_Address | VARCHAR (200) |     | Address of the rider |
| Contact_Number | VARCHAR (10) |     | Phone number |
| License_Number | VARCHAR (50) |     | License number of the rider |
| **Dependent** | Employee_Number | INT | Foreign Key | Primary key of Rider table |
| Dependent_Name | VARCHAR (50) | Composite Primary Key | To identify the dependent |
| DOB | DATE |     | Date of Birth |
| Relationship_to_the_rider | VARCHAR (50) |     | What is the relationship between riders and dependents |
| **Motorbike** | Vehicle_Registration_Number | VARCHAR (20) | Primary Key | To identify the motorbike uniquely |
| Vehicle_Registered_Date | DATE |     | The date when the motorbike was registered |
| Brand | VARCHAR (50) |     | The brand name of the motorbike |
| Model | VARCHAR (50) |     | The model’s name of the motorbike |
| Engine_Number | VARCHAR (20) |     | The engine number of the motorbike |
| **Motorbike_Color** | Vehicle_Registration_Number | VARCHAR (20) | Foreign Key | Primary key of Motorbike table |
| Color | VARCHAR (10) | Composite Primary Key | The color of the motorbike |
| **Bike_Assignment** | Assignment_ID | INT | Primary Key | To identify the bike assignment uniquely |
| Employee_Number | INT | Foreign Key | Primary key of Rider table |
| Vehicle_Registration_Number | VARCHAR (20) | Foreign Key | Primary key of Motorbike table |
| Date_Used | DATE |     | The date when the bike was used for delivery |
| Shift | VARCHAR (10) |     | The shift of the rider; whether it is daytime or nighttime |
| Meter_Reading_When_Assigned | INT |     | The meter reading of the bike when it was assigned for the delivery |
| Meter_Reading_When_Returned | INT |     | The meter reading of the bike when it was returned after the delivery |
