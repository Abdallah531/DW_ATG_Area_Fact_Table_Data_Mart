# Data Warehousing Project 
## 🎯 Project Overview
This project involves the design and implementation of a comprehensive Data Warehouse (DWH) for a retail environment. It covers the full lifecycle from dimensional modeling to ETL development and business intelligence dashboarding.
### 🔗 Resources
* **Dataset URL:** [Access Dataset](https://drive.google.com/file/d/10Ikpr_T8wgcFru-WgUABaAecq3VYjvKY/view?usp=share_link)
* **Tools Used:** SQL Server, SQL Server Integration Services (SSIS), Power BI/Dashboarding Tools.
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

## 📐 Phase 1: Dimensional Modeling
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

## 🔄 Phase 2: ETL & Implementation
[cite_start]The ETL process was built using **SSIS Packages** to transform operational data into the DWH schema[cite: 79, 88].

### 🛠️ SSIS Package Structure
1. [cite_start]**Staging (STG):** Truncates existing tables and loads data from the source[cite: 113, 162].
   * [cite_start]Packages: `Customer_STG`, `Orders_STG`, `Product_STG`[cite: 93, 105, 180, 274].
2. **Dimension Loading:** Loads data from Staging into the final Dimension tables.
   * [cite_start]Packages: `from source to DIM_Staffs`, `from source to timeDim`[cite: 94, 95, 96].
3. [cite_start]**Fact Loading:** Populates the Fact tables with measures and foreign keys[cite: 97, 222].
   * [cite_start]Packages: `load Fact Order table`, `Load Fact Staff product`, `load Fact customer brand`[cite: 98, 101, 177, 181].
