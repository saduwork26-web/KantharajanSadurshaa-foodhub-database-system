# **Section 1: Introduction**

## **Purpose**

This document refers the user requirements of the FoodHub Database System for the newly developed FoodHub branch in Sri Lanka. It serves as the foundation for design, development, and testing phases. The document is intended for development team and stakeholders of this project. It captures stakeholders of this project, user classes in this project, functional requirements, non-functional requirements, assumptions, and constraints in this project. This will ensure the final system meets the business needs of FoodHub Database System and provides a reference point for all stakeholders.

## **Scope**

The system covers the delivery management only for the initial phase.

- Customer Registration & Management
- Staff Member Registration
- Rider Registration & Management
- Dependent Details Management
- Order Placement
- Order Tracking
- Delivery Details Management
- Food Ingredients Management (upon the request)
- Motorbike Assignment & Management
- Motorbike Meter Reading Records

If the system implementation was successful, in future they will enhance the performance of the FoodHub Database System by integrating Human Resource Management & Finance Management.

## **Business Context**

FoodHub Company is a well-known fast-food company locate in United State of America. It started 14 years ago & the company management decided to open branches worldwide. So, they are going to open a new branch in Sri Lanka as well. The company decided to hire a local database expert to develop a Database Management system to assist in this project for decision making. Therefore, the data should maintain accuracy & the consistency throughout the data life cycle. The FoodHub company only provides food delivery service, and they won’t offer/sell food items in the outlets.

The new branch does not have an integrated system that manages the delivery operations at present. Information about customers, orders, riders, and motorbikes could be kept in disconnected spreadsheets or manually, causing data duplication, errors, and inefficiency. If it doesn't have a proper database system, it will not be able to make informed business decisions, track deliveries accurately, and grow its business. So, FoodHub has engaged a database specialist to work on designing and developing a Delivery Management System which will act as an ERP backbone for future HR and Finance integration.

# **Section 2: Stakeholders**

- Customer: A customer can place the order and get the order delivered home.
- Staff Member: Enter the order of the customer.
- Rider: Delivers the order to the customer’s address
- Rider Supervisor: Assign the rider for the delivery according to their shift with the company motorbike.
- Database Admin: Manage the records of the FoodHub Database.
- IT Support Staff: Troubleshoot the issues that occurred in the FoodHub System.
- FoodHub Management: Deal with the decision-making process of the System for improvements and provide the financial support for the development.
- Lecturer: Evaluate the system design.

# **Section 3: User Classes**

- Customer:

- Role: End-user - makes food orders for delivery.

- Technical Skill Level: Basic to intermediate (comfortable with using mobile apps and websites).

- Frequency of Use: Occasionally (when they want to order food, this is likely a few times a month).

- Key Needs:
    - Fast and easy to use menu and ordering system.
    - Up-to-date information on food availability and order delivery.
    - The capability to display ingredient information and choose payment options.

- Pain Points:
    - Order interfaces that take too long or are not intuitive.
    - Limited information about the content of the food or the time of food availability.

- Staff Member:

- Role: Order taking, handling enquiries, data entry.

- Technical Skill Level: Intermediate (Training carried out on the specific desktop application).

- Frequency of Use: Daily; high volume (use throughout their shift).

- Key Needs:
    - Quick and mistake-free order entry system for customers.
    - Customer information, order history and instant menu availability.
    - The ability to be able to update order statuses and record dispatch times easily.

- Pain Points:
    - The responsiveness of the system will slow down during peak hours.
    - Entering data repeatedly or accessing multiple screens to enter one order.
- Rider:

- - Role: To pick up food and bring it to the customer's address.

- - Technical Skill Level: Basic (must have basic mobile or internet-based interface).

- - Frequency of Use: Daily (on their shifts).

- - Key Needs:
        - Step-by-step delivery instructions and customer location is clear.
        - Quick log of their motor bike and start/end meter readings.
        - Being able to change order status to "Delivered" when order is completed.

- - Pain Points:
        - Missing addresses or contact information.
        - Intricate processes to process bike and meter logins/offing at the beginning/end of a shift.

- Rider Supervisor:

- - Role: Operational manager, who is responsible for the riders, motorbikes and rider records.

- - Technical Skill Level: Intermediate to Advanced.

- - Frequency of Use: Daily

- - Key Needs:
        - Availability Dashboard: Dashboard for checking the availability of the riders and allocating motorbikes on a shift basis.
        - Registration of new riders, updating of rider details and management of dependent riders.
        - Tools for checking and confirming meter readings taken by riders.

- - Pain Points:
        - The need to manually extend the rider details to the bike, resulting in schedule conflicts.
        - Faulty or non-reading meters lead to disputes about fuel/maintenance.

- Database Admin:

- - Role: Technical specialist with the role of providing security, integrity and maintaining the database.

- - Technical Skill Level: Expert

- - Frequency of Use: Weekly (for routine maintenance) or as needed (for troubleshooting).

- - Key Needs:
        - Stronger capability to build user groups and assign strong access rights (RBAC).
        - An effective backup plan for the databases.
        - Audit trails and view of system logs to detect unauthorized access.

- - Pain Points:
        - Unsafe practices or illegal entry into confidential information.
        - Failure to back up data or hardware failures.

- FoodHub Management:

- - Role: Decisionmakers (CEO, Branch Manager, etc.) who make decisions on the profitability and growth of the business.

- - Technical Skill Level: Basic to Intermediate (must be able to access dashboards and reports).

- - Frequency of Use: Weekly/Monthly.

- - Key Needs:
        - High level, easy to read daily orders and sales reports.
        - Analysis of rider performance to determine who is the best and who needs training.
        - Revenue tracking for informed business decision making in Sri Lanka branch.

- - Pain Points:
        - Lack of reliable, real-time data to make quick business decisions.
        - Using secondhand information provided by staff or manual spreadsheets.

# **Section 4: Functional Requirements**

|     |     |
| --- | --- |
| FR1 | The system shall allow customers to log in. |
| FR2 | The system shall allow customers to place orders. |
| FR3 | The system shall allow customers to get updates of food availability. |
| FR4 | The system shall allow customers to confirm orders. |
| FR5 | The system shall allow customers to request ingredients. |
| FR6 | The system shall allow customers to view order summary. |
| FR7 | The system shall allow customers to view delivery details. |
| FR8 | The system shall allow customers to view payment receipts. |
| FR9 | The system shall allow customers to choose payment method. |
| FR10 | The system shall allow staff members to log in. |
| FR11 | The system shall allow staff members to enter orders. |
| FR12 | The system shall allow staff members to update the food items on the menu. |
| FR13 | The system shall allow staff members to update the ingredients of the food items. |
| FR14 | The system shall allow staff members to view customer details. |
| FR15 | The system shall allow staff members to view order details. |
| FR16 | The system shall allow staff members to register new customers. |
| FR17 | The system shall allow staff members to update customer details. |
| FR18 | The system shall allow staff members to update the order status. |
| FR19 | The system shall allow staff members to record the order dispatch time. |
| FR20 | The system shall allow riders to log in. |
| FR21 | The system shall allow riders to view order details. |
| FR22 | The system shall allow riders to provide the bike_used details. |
| FR23 | The system shall allow riders to mark meter reading when bike is assigned during the shift. |
| FR24 | The system shall allow riders to mark meter reading when bike is returned after the delivery. |
| FR25 | The system shall allow rider supervisor to log in. |
| FR26 | The system shall allow rider supervisors to register new riders. |
| FR27 | The system shall allow rider supervisor to update rider details. |
| FR28 | The system shall allow rider supervisors to register new motorbikes. |
| FR29 | The system shall allow rider supervisor to assign motorbikes to the riders according to the shift. |
| FR30 | The system shall allow rider supervisor to view and verify the meter reading when bike is assigned during the shift. |
| FR31 | The system shall allow rider supervisor to view and verify the meter reading when bike is returned after the delivery. |
| FR32 | The system shall allow database admin to log in. |
| FR33 | The system shall allow database admin to manage user groups. |
| FR34 | The system shall allow database admin to perform database backups. |
| FR35 | The system shall allow management to log in. |
| FR36 | The system shall allow management to view daily order reports. |
| FR37 | The system shall allow management to view rider performance reports. |
| FR38 | The system shall allow management to view sales and revenue reports. |

# **Section 5: Non-Functional Requirements**

Performance:

- NFR1: The system must process order entries in under 2 seconds.
- NFR2: The system must generate daily reports in under 5 seconds.
- NFR3: The system must support at least 30 users at the same time.

Reliability:

- NFR4: The system must keep 99% uptime during business hours.
- NFR5: The system must run automatic database backups every day.
- NFR6: The system must recover from unexpected failures within 1 hour.

Security:

- NFR7: The system must encrypt all user passwords.
- NFR8: The system must enforce role-based access control (RBAC).
- NFR9: The system must log all user activity for audit purposes.

Usability:

- NFR10: The system must show clear, user-friendly error messages.
- NFR11: The system must let staff complete an order in less than 1 minute.

Maintainability:

- NFR12: The database must be normalized to Third Normal Form (3NF).
- NFR13: The system must use consistent naming rules for tables and columns.

Scalability:

- NFR14: The system must support future integration with HR and Finance modules.

Data Integrity:

- NFR15: The system must enforce referential integrity through foreign keys.
- NFR16: The system must validate all data at entry points.

# **Section 6: Assumptions and Constraints**

## **6.1 Assumptions**:

- Customers can use a specific app to place the order. Also, if the customer finds difficulty in placing orders especially elders, they could place the orders via calls then the staff member will enter the order.
- Staff members can register new customers.
- Riders can log in to the system and view the order details.
- A rider supervisor can login to the system, register new motorbikes and maintain rider details.
- Database admin can login to the system and perform maintenance tasks.
- FoodHub management can login to the system and view the reports.

## **6.2 Constraints:**

- The system is constrained by Microsoft SQL Server for database management and C#.NET WinForms to design the interfaces.
- The system is constrained by covering the Phase 1, which is Delivery Management, because the HR and Finance modules are out of the scope, since they have planned to develop them after the successful implementation of Phase 1.
- The system is constrained to be completed within the current academic timeframe.
- The system is constrained to comply with data privacy and protection regulations to ensure the security concerns of the users.
