# Data Warehousing Project 
## 🎯 Project Overview
This project involves designing a **Dimensional Model** for a Data Warehouse to support business intelligence and decision-making processes. 

### 🔗 Project Assets
* **Dataset:** [Download Dataset](https://drive.google.com/file/d/10Ikpr_T8wgcFru-WgUABaAecq3VYjvKY/view?usp=share_link)
* **ERD:** Includes the Entity Relationship Diagram for the source database.

---

## 📈 Business Processes & Objectives
We are modeling the following core business processes:
* **Sales Analysis:** Insights into product/store performance and customer segments.
* **Inventory Management:** Tracking stock levels and movements across stores.
* **Customer Segmentation:** Demographic and behavioral analysis for marketing.
* **Workforce Management:** Tracking employee performance and training needs.
* **Financial Reporting:** Monitoring revenue, expenses, and profitability.

### ❓ Analytical Questions (Example Statements)
* What were the sales of a certain brand for each store last month?
* How many orders did each staff member complete last week?
* How many customers bought a specific brand across all stores last year?
* What is the count of different categories held in stock last year?
* What is the daily number of orders requested by customers per staff member per store?

---

## 📐 Dimensional Model Design

* The business processes modeled include sales performance, inventory management, customer segmentation, and employee productivity.
![licensed-image](https://github.com/user-attachments/assets/d57c0604-e395-4def-aef6-96bfd2456634)

### 🔹 Dimensions
* **Time Dim:** Date details (Day, Month, Year).
* **Staffs Dim:** First Name, Last Name, Phone, Email, and Status.
* **Store Dim:** Store Name, Phone, Email, City, Street, State, and ZIP Code.
* **Customer Dim:** First Name, Last Name, Phone, Email, City, Street, and State.
* **Order Dim:** Customer info, Order Status, Order Date, Required Date, Shipped Date, Store ID, Staff ID.
* **Product Dim:** Product Name, Brand ID, Category ID, Model Year, and List Price.

### 📊 Fact Tables
| Fact Table | Measure | Description |
| :--- | :--- | :--- |
| **Orders Fact** | `Order Num` | The total count of orders requested. |
| **Customers Brands Fact** | `Customer Num` | Number of customers who bought a specific brand. |
| **Staff Orders Fact** | `Staff Orders Num` | Number of orders processed by each staff member. |
