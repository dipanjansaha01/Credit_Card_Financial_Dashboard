# 📊 Credit Card Financial Dashboard - Power BI

## 🔍 Overview
The **Credit Card Financial Dashboard** is an interactive Power BI report designed to analyze credit card transactions, customer demographics, and financial performance. This project provides insights into revenue, customer acquisition cost, transaction trends, and customer satisfaction.

## 📷 Dashboard Snapshots
- [Credit Card Customer Report (PDF)](./Credit%20Card%20Customer%20Report.pdf)
- [Credit Card Transaction Report (PDF)](./Credit%20Card%20Transaction%20Report.pdf)

These reports showcase key dashboard screenshot and insights from the analysis.

## 📌 Features
- **Transaction Analysis:** Revenue, transaction count, and expenditure breakdown.
- **Customer Insights:** Analysis based on job type, education level, age group, and marital status.
- **Card Category Performance:** Revenue and transactions across different card categories (Blue, Silver, Gold, Platinum).
- **Geographical Trends:** Customer distribution across different states.
- **Time-Series Analysis:** Weekly and quarterly revenue and transaction trends.

## 🛠️ Tech Stack
- **Power BI** (Data Visualization)
- **MySQL** (Database)
- **CSV Files** (Data Source)
- **DAX & Power Query** (Data Processing)

## 📂 Data Source
The project utilizes structured CSV files for transaction and customer data:
1. `credit_card.csv` - Contains transaction details such as revenue, transaction amount, and card usage patterns.
2. `customer.csv` - Includes customer demographics, income levels, and satisfaction scores.
3. Additional datasets (`cc_add.csv`, `cust_add.csv`) for extended insights.

## 🏗️ Database Schema
Two primary tables are used for analysis:

### `cc_detail` (Credit Card Transactions)
| Column Name            | Data Type          | Description |
|------------------------|-------------------|-------------|
| Client_Num            | INT               | Unique customer identifier |
| Card_Category         | VARCHAR(20)       | Card type (Blue, Silver, Gold, Platinum) |
| Annual_Fees          | INT               | Annual card fee |
| Activation_30_Days    | INT               | Activated within 30 days (1 = Yes, 0 = No) |
| Customer_Acq_Cost    | INT               | Cost to acquire the customer |
| Week_Start_Date      | DATE              | Transaction week start date |
| Total_Trans_Amt      | INT               | Total transaction amount |
| Total_Trans_Ct       | INT               | Number of transactions |
| Avg_Utilization_Ratio | DECIMAL(10,3)    | Credit utilization ratio |
| Interest_Earned      | DECIMAL(10,3)     | Interest revenue earned |

### `cust_detail` (Customer Demographics)
| Column Name            | Data Type         | Description |
|------------------------|------------------|-------------|
| Client_Num            | INT              | Unique customer identifier |
| Customer_Age         | INT              | Age of the customer |
| Gender               | VARCHAR(5)       | Gender (M/F) |
| Income               | INT              | Annual income |
| Marital_Status       | VARCHAR(20)      | Married, Single, etc. |
| Education_Level      | VARCHAR(50)      | Graduate, High School, etc. |
| Car_Owner           | VARCHAR(5)       | Owns a car (Yes/No) |
| House_Owner         | VARCHAR(5)       | Owns a house (Yes/No) |
| Cust_Satisfaction_Score | INT           | Satisfaction rating |

## 🔄 Data Import (MySQL)
```sql
LOAD DATA INFILE 'D:/credit_card.csv'
INTO TABLE cc_detail
FIELDS TERMINATED BY ',' 
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;
```
```sql
LOAD DATA INFILE 'D:/customer.csv'
INTO TABLE cust_detail
FIELDS TERMINATED BY ',' 
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;
```

## 📊 Power BI Visuals
The dashboard includes:
- **Revenue Breakdown:** Total revenue by expenditure type, job category, and education level.
- **Customer Segmentation:** Analysis by gender, age, and salary group.
- **Card Performance:** Revenue and transaction analysis per card category.
- **Trend Analysis:** Weekly and quarterly trends in revenue and transactions.
- **State-Wise Insights:** Performance across different states.


## 🚀 How to Use
1. **Import Data:** Ensure MySQL tables are populated using the provided CSV files.
2. **Open Power BI Report:** Load the `.pbix` file in Power BI Desktop.
3. **Connect to Database:** Configure the data source to link with MySQL.
4. **Refresh Data:** Click "Refresh" in Power BI to update the visualizations.
5. **Explore Insights:** Use slicers and filters to interact with the dashboard.

## 💡 Key Insights
- The **Platinum** card category generates the highest interest revenue.
- **Businessmen & White-collar** professionals contribute the most to total revenue.
- **Quarterly trends** indicate consistent revenue generation with seasonal spikes.
- **Customer satisfaction** correlates with income and transaction frequency.

## 📌 Future Enhancements
- Integrate **real-time data updates** for live tracking.
- Deploy a **Power BI Service dashboard** for web access.
- Implement **predictive analytics** for revenue forecasting.

