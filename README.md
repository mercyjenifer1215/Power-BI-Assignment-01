# 📊 Project Title: Superstore Sales and Profit Analysis – Power BI

An interactive Power BI analysis of sales, profit, customer orders, product categories, and monthly sales targets to identify business performance, profitability trends, and opportunities for improvement.

## 📑 Table of Contents

- [Project Overview](#-project-overview)
- [Data Sources & Architecture](#-data-sources--architecture)
- [Data Transformation (ETL)](#-data-transformation-etl)
- [Data Model & DAX](#-data-model--dax)
- [Dashboard Features](#-dashboard-features)
- [Key Insights](#-key-insights)
- [Four Types of Analysis](#-four-types-of-analysis)
- [Business Recommendations](#-business-recommendations)
- [How To Use](#-how-to-use)

---

## 🎯 Project Overview

- **Business Problem:** The business needs to understand its sales performance, profitability, customer orders, product category performance, and monthly sales targets to identify areas requiring improvement.
- **Objective:** Analyze sales and profit data using Power BI to identify business trends, monitor performance, and support data-driven decision-making.
- **Target Audience:** Business owners, sales managers, business analysts, and management teams.
- **Tools Used:** Microsoft Power BI Desktop, Power Query Editor, and CSV files.

## 🗃️ Data Sources & Architecture

### Data Sources

The project uses three CSV datasets:

| Dataset | Description | Records |
|---|---|---:|
| List of Orders | Customer, order date, city, state, and order details | 500 valid rows |
| Order Details | Category, sub-category, sales amount, profit, and quantity | 1,500 rows |
| Sales Target | Monthly sales targets by category | 36 rows |

- **Source Systems:** CSV files.
- **Data Volume:** 2,036 valid records across three original datasets.
- **Time Period:** April 2018 – March 2019.
- **Storage Mode:** Import Mode.
- **Data Preparation:** Power Query Editor.

## ⚙️ Data Transformation (ETL)

**Tool Used:** Power Query Editor.

The following data cleaning and transformation operations were performed:

1. **Row Filtering:** Kept the first 500 rows in the List of Orders table.
2. **Data Type Conversion:** Changed Amount and Target columns to Fixed Decimal Number.
3. **Text Formatting:** Converted Customer Name into Proper Case.
4. **Column Creation:** Merged City and State to create a Location column.
5. **Custom Column:** Created Profit Margin using Profit / Amount.
6. **Conditional Column:** Created Profit Status with three categories:
   - Profit
   - Loss
   - Break-Even
7. **Data Merging:** Merged List of Orders and Order Details using Order ID to create Orders Data.
8. **Missing Data Handling:** Identified and removed completely blank rows from List of Orders. Checked the remaining tables for missing values.
9. **Duplicate Handling:** Retained repeated Order IDs because they represent multiple product entries within an order.
10. **Sorting:** Sorted Order Date in descending order.
11. **Filtering:** Applied a State filter to analyze Tamil Nadu orders.
12. **Grouping and Aggregation:** Created summary tables for:
    - Count of Order ID
    - Average Profit by Category
    - Total Amount by Sub-Category
    - Total Target by Month

## 🧠 Data Model & DAX

### Data Model

The project uses a relational data model connecting three original datasets.

**Relationships established:**

| Relationship | Key Column | Cardinality |
|---|---|---|
| List of Orders → Order Details | Order ID | One-to-Many (1:*) |
| Order Details → Sales Target | Category | Many-to-Many (*:*) |

Both relationships were checked using Manage Relationships to ensure they were active.

**Calculated Columns:**

Profit Margin:
```powerquery
if [Amount] = 0 then null else [Profit] / [Amount]
```

Profit Status:
```powerquery
if [Profit] < 0 then "Loss"
else if [Profit] = 0 then "Break-Even"
else "Profit"
```

**Aggregation Operations:**

- Count Rows – Order Count
- Average – Profit by Category
- Sum – Amount by Sub-Category
- Sum – Target by Month

## 🖥️ Dashboard Features

The analysis supports the following reporting features:

- **Sales Overview:** Total sales, total profit, and quantity sold.
- **Category Analysis:** Sales and profit comparison across Clothing, Electronics, and Furniture.
- **Sub-Category Analysis:** Identification of high-profit and loss-making products.
- **Geographical Analysis:** State-wise sales and profit performance.
- **Profitability Analysis:** Profit Margin and Profit Status classification.
- **Monthly Target Analysis:** Monthly sales target comparison.
- **Interactive Filtering:** Analysis by state, category, sub-category, and order date.

## 💡 Key Insights

1. **Total Sales:** 431,502.
2. **Total Profit:** 23,955.
3. **Total Quantity Sold:** 5,615.
4. **Overall Profit Margin:** Approximately 5.55%.
5. **Highest Sales Category:** Electronics, with 165,267 in sales.
6. **Highest Profit Category:** Clothing, with 11,163 in profit.
7. **Highest Profit Sub-Category:** Printers, generating 5,964 in profit.
8. **Highest Loss Sub-Category:** Tables, recording a loss of 4,011.
9. **Profit Status:** 950 profitable records, 503 loss-making records, and 47 break-even records.
10. **Highest State-Wise Profit:** Maharashtra, generating 6,176.

## 📈 Four Types of Analysis

### 1. Descriptive Analysis – What Happened?
- Examined total sales, profit, and quantity sold.
- Identified the highest-performing category and state.
- Analyzed overall business performance.

### 2. Diagnostic Analysis – Why Did It Happen?
- Identified loss-making products and categories.
- Examined differences in category-wise profitability.
- Investigated geographical performance variations.

### 3. Predictive Analysis – What Might Happen?
- Reviewed historical monthly sales targets.
- Identified categories requiring future performance monitoring.
- Used historical trends to support future planning.

### 4. Prescriptive Analysis – What Should Be Done?
- Recommended improving Furniture profitability.
- Suggested reviewing pricing and discounts for loss-making products.
- Recommended monitoring monthly sales against targets.
- Suggested focusing on high-profit products.

## 🚀 Business Recommendations

- Improve profitability in the Furniture category.
- Review pricing and discount strategies for Tables.
- Investigate losses in Electronic Games.
- Focus on high-profit products such as Printers and Bookcases.
- Monitor state-wise sales and profitability.
- Compare actual sales performance against monthly targets.
- Use Profit Margin to monitor business profitability.

## 🚀 How To Use

1. **Prerequisites:** Install Microsoft Power BI Desktop.
2. **Clone Repository:** Download or clone this GitHub repository.
3. **Open Project:** Open the `.pbix` Power BI project file.
4. **Data Sources:** Keep the three CSV files in an accessible folder.
5. **Data Refresh:** Update the source paths under Data Source Settings if required.
6. **Explore Dashboard:** Use filters and interactive visuals to explore sales, profit, category, and geographical performance.

---

## 🛠️ Technologies Used

- Microsoft Power BI Desktop
- Power Query Editor
- CSV Dataset
- Data Cleaning and Transformation
- Data Modeling
- Data Visualization
- Business Intelligence

## 📝 Project Conclusion

This project demonstrates how raw sales data can be transformed into meaningful business insights using Power BI. Through data cleaning, transformation, relationship modeling, grouping, and analysis, the project identifies sales trends, profitable categories, loss-making products, and business improvement opportunities.

The analysis supports better business decisions through Descriptive, Diagnostic, Predictive, and Prescriptive Analytics.

---

**Project Type:** Data Analytics / Business Intelligence  
**Tool:** Microsoft Power BI  
**Domain:** Sales and Business Performance Analysis
