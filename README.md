# car-sales-dashboard-powerbi
# 🚗 Car Sales Dashboard – Power BI

## 📌 Background
Our company is a car dealership selling various car models across multiple regions. To effectively track and analyze sales performance, we developed a dynamic and interactive Car Sales Dashboard using Power BI.

---

## 🎯 Project Objective
The objective of this project is to design and develop a comprehensive dashboard that visualizes critical KPIs related to car sales performance. The dashboard enables real-time tracking of sales metrics, identifies trends, and supports data-driven decision-making.

---

# 📊 Problem Statement 1: KPI Requirements

The dashboard provides insights into the following key performance indicators:

## 🔹 Sales Overview
- Year-to-Date (YTD) Total Sales
- Month-to-Date (MTD) Total Sales
- Year-over-Year (YOY) Growth in Total Sales
- Difference between YTD Sales and Previous Year-to-Date (PTYD) Sales

## 🔹 Average Price Analysis
- YTD Average Price
- MTD Average Price
- YOY Growth in Average Price
- Difference between YTD Average Price and PTYD Average Price

## 🔹 Cars Sold Metrics
- YTD Cars Sold
- MTD Cars Sold
- YOY Growth in Cars Sold
- Difference between YTD Cars Sold and PTYD Cars Sold

---

# 📈 Problem Statement 2: Charts & Visualizations

## 1️⃣ YTD Sales Weekly Trend
- Line Chart
- X-axis: Week Number
- Y-axis: Total Sales Amount

## 2️⃣ YTD Total Sales by Body Style
- Pie Chart
- Displays contribution of each car body style

## 3️⃣ YTD Total Sales by Color
- Pie Chart
- Shows distribution of sales by car color

## 4️⃣ YTD Cars Sold by Dealer Region
- Map Visualization
- Displays geographic sales distribution

## 5️⃣ Company-Wise Sales Trend (Grid View)
- Tabular Grid
- Company Name
- YTD Sales
- % Contribution

## 6️⃣ Detailed Sales Data Grid
- Car Model
- Body Style
- Color
- Sales Amount
- Dealer Region
- Date of Sale
- Transmission
- Engine Type

---

# 🛠 Tools & Technologies Used
- Power BI
- DAX (Time Intelligence)
- Data Modeling
- SQL / PostgreSQL
- Excel

---

# 📐 Key DAX Measures

```DAX
YTD Sales = 
CALCULATE(
    SUM(Sales[Sales Amount]),
    DATESYTD(Date[Date])
)

MTD Sales =
CALCULATE(
    SUM(Sales[Sales Amount]),
    DATESMTD(Date[Date])
)

PTYD Sales =
CALCULATE(q
    [YTD Sales],
    SAMEPERIODLASTYEAR(Date[Date])
)

YOY Growth % =
DIVIDE(
    [YTD Sales] - [PTYD Sales],
    [PTYD Sales]
)
