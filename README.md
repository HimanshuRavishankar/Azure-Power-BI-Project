
# 👕 Men's Apparel Analysis – Power BI Dashboard

**🔗 Project Repository**  
[GitHub Link][(https://github.com/HimanshuRavishankar/Azure-Power-BI-Project.git)]

**🔗 Project Portfolio** 
https://project.novypro.com/YvrZxq
---

## 🎯 Objective

To design a dynamic, real-time business intelligence dashboard for analyzing the performance of men’s apparel brands using end-to-end data integration and modeling. This includes Azure SQL Database connectivity, advanced Power BI transformations, and insightful brand-level KPIs like discount percentages, profit margins, and sales trends.

---

## 🔄 Workflow & Implementation Steps

### 1. **Data Integration via Azure SQL and SSMS**

- Connected a **Microsoft Azure SQL Database** to **SQL Server Management Studio (SSMS)** using the same server credentials.
- Configured the **firewall settings** to allow remote connections and enable successful query execution in SSMS.
- Imported the `.csv` file containing raw apparel data using **Flat File Import Wizard**.
- Cleaned and preprocessed the dataset in SSMS by removing special characters and formatting inconsistencies.
- Verified the updates using the **Azure SQL Query Editor** and linked the database to Power BI via direct server connection for real-time access.

---

### 2. **Data Preparation in Power BI (Power Query)**

- Connected Power BI to Azure SQL Database.
- Filtered out null entries (`NA`) in critical fields like `Sales Price`.
- Created a **custom imputation logic**:
  - Generated a conditional column named `Factor`, where if `Original Price` is null, it’s replaced with `1.5` (to represent markup over `Sales Price`).
  - Created a calculated column `Sales * Factor`, representing an **estimated Marked Price** in cases of missing data.
  - Replaced nulls in the `Original Price` with these derived values to form a cleaned `Marked Price` column.

---

### 3. **Feature Engineering (Table View)**

- **Discount %** = `(Marked Price - Sales Price) / Marked Price * 100`
- **Profit Price** = `RANDBETWEEN(2, 17)` – simulated approximate profit margin percentage.
- **Cost Price** = `Sales Price - (Profit Price% of Sales Price)`

This structured engineering allowed the dataset to include **estimated financial metrics** while maintaining analytical integrity.

---

### 4. **Dashboard Design (Report View)**

#### 🧾 Page 1: **Available Brands Overview**
- Featured a full-screen **multi-row card** listing all available brands.
- Styled using custom visual formatting to reflect a retail landing-page look.

#### 📊 Page 2: **Performance Insights Dashboard**
- **Stacked Bar Chart**: Top 5 brands by **average discount %**
- **Donut Chart**: Top 5 brands with the **highest number of variants**
- **Ribbon Chart**: Top 5 brands by **average sales price**
- **Area Chart**: Top 5 brands by **average profit %**
- **Pie Chart**: Bottom 5 brands by **average profit %**

These visualizations provide a comprehensive 360-degree view of **brand-level performance**, **pricing strategies**, and **profitability**.

> 📸 **Dashboard Screenshots:**  
**Page 1 – Brand Overview**  
![Report Page 1](Report%20Page%201.png)

**Page 2 – Performance Dashboard**  
![Report Page 2](Report%20Page%202.png)

---

## 🛠️ Tools & Technologies Used

- **Database**: Azure SQL Database, SQL Server Management Studio (SSMS)
- **Preprocessing & Modeling**: Power BI (Power Query, Data View)
- **Visualization**: Power BI Desktop
- **Languages & Functions**: Power Query M, DAX, SQL (Azure), RANDBETWEEN, IF, Custom Columns

---

## 🌟 Outcome

- Delivered an interactive business intelligence dashboard focused on brand-level metrics in the **men’s T-shirt apparel sector**.
- Enabled real-time analytics by integrating cloud-hosted SQL data into Power BI.
- Designed with an emphasis on **UI aesthetics**, **data storytelling**, and **KPI-driven insights**.

---

## 🧠 Key Learnings

- Integration of **cloud databases (Azure SQL)** with BI tools for scalable analytics.
- Creative data imputation using conditional logic in Power BI.
- Enhanced DAX usage to derive meaningful financial metrics.
- Dashboard storytelling techniques tailored for **retail brand performance analysis**.
