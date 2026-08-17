# Blinkit-Sales-Outlet-Performance-Dashboard
# 🛒 Blinkit Sales & Outlet Performance Dashboard

An interactive **Power BI dashboard** developed to analyze Blinkit's grocery sales performance across **product categories, outlet types, outlet sizes, outlet locations, and establishment years**.

This project demonstrates an end-to-end **data analytics workflow** — from data cleaning and transformation in Power Query to KPI creation using DAX and interactive business intelligence reporting in Power BI.

---

## 📊 Dashboard Preview

![Blinkit Sales & Outlet Performance Dashboard](screenshots/dashboard_overview.png)

> **Interactive Power BI dashboard** for analyzing sales, product performance, outlet characteristics, and customer ratings.

---

## 🎯 Project Objective

The objective of this project is to analyze Blinkit's grocery sales data and identify the factors influencing sales performance across different products and outlets.

The dashboard was designed to answer questions such as:

* Which product categories contribute the most to sales?
* Which outlet types generate the highest revenue?
* How does outlet size affect sales?
* Which outlet locations perform best?
* How does sales performance vary based on outlet establishment year?
* How do product characteristics such as fat content relate to sales and ratings?
* Which outlet and product segments should receive greater business attention?

---

## 🗂️ Dataset

**Source file:** `BlinkIT_Grocery_Data.xlsx`

**Format:** Excel

**Sheet:** `BlinkIT Grocery Data`

### Dataset Overview

| Attribute         | Details |
| ----------------- | ------: |
| Sales records     |   8,523 |
| Unique items      |   1,559 |
| Unique outlets    |      10 |
| Number of columns |      12 |

### Key Columns

| Column                      | Description                                |
| --------------------------- | ------------------------------------------ |
| `Item Identifier`           | Unique identifier for each item            |
| `Item Type`                 | Product category                           |
| `Item Fat Content`          | Fat-content classification                 |
| `Item Weight`               | Weight of the product                      |
| `Item Visibility`           | Percentage of shelf visibility             |
| `Outlet Identifier`         | Unique outlet identifier                   |
| `Outlet Establishment Year` | Year the outlet was established            |
| `Outlet Size`               | Outlet size classification                 |
| `Outlet Location Type`      | Tier classification of the outlet location |
| `Outlet Type`               | Type of retail outlet                      |
| `Sales`                     | Sales amount                               |
| `Rating`                    | Customer rating                            |

---

## 🧹 Data Cleaning & Transformation

The raw dataset was prepared using **Power Query** before building the dashboard.

### Data preparation included:

* Reviewing the structure and quality of the raw dataset
* Checking and correcting data types
* Handling inconsistent categorical values
* Standardizing `Item Fat Content` categories
* Reviewing missing values
* Preparing fields for analysis and visualization
* Creating a clean dataset for Power BI reporting

### Data Quality Issue Identified

The original `Item Fat Content` column contained inconsistent labels such as:

```text
LF
Low Fat
low fat
Regular
reg
```

These values represent the same underlying categories and therefore need to be standardized before analysis to avoid inaccurate grouping.

---

## 📐 DAX Measures

The dashboard uses DAX measures to calculate the primary KPIs.

### Total Sales

```DAX
Total Sales =
SUM('BlinkIT Grocery Data'[Sales])
```

### Average Sales

```DAX
Avg Sales =
AVERAGE('BlinkIT Grocery Data'[Sales])
```

### Average Rating

```DAX
Avg Rating =
AVERAGE('BlinkIT Grocery Data'[Rating])
```

### Number of Items

```DAX
No. Of Items =
COUNTROWS('BlinkIT Grocery Data')
```

### Average Visibility

```DAX
AVG_visibility =
AVERAGE('BlinkIT Grocery Data'[Item Visibility])
```

---

## 📊 Key Performance Indicators

The dashboard provides a high-level view of overall business performance.

| KPI                |        Value |
| ------------------ | -----------: |
| **Total Sales**    | **$507.90K** |
| **Average Sales**  |     **$140** |
| **No. of Items**   |    **3,631** |
| **Average Rating** |      **4.0** |

> The KPI values shown above reflect the dashboard's current filtering state.

---

## 📈 Dashboard Analysis

### 1. Fat Content Analysis

**Visualization:** Donut Chart + Interactive Measure Selection

The dashboard analyzes performance based on product fat content, comparing:

* Low Fat
* Regular

A field-parameter-based selector allows the visual to switch between:

* Average Sales
* Number of Items
* Average Rating
* Total Sales

This allows users to analyze the same dimension from multiple business perspectives without creating separate visuals for every metric.

---

### 2. Item Type Analysis

**Visualization:** Bar Chart

The dashboard compares performance across **16 item categories**, including categories such as:

* Snacks
* Dairy
* Breakfast
* Frozen Foods
* Fruits & Vegetables
* Household
* and other product categories.

This helps identify which product categories contribute most significantly to overall sales and item volume.

---

### 3. Outlet Establishment Analysis

**Visualization:** Line Chart

The dashboard analyzes total sales based on the **year in which an outlet was established**.

A noticeable pattern is that several older outlets, particularly those established around **2012 and earlier**, generate substantially higher sales than many newer outlets.

This can help investigate whether outlet maturity, location, size, or outlet type contributes to sales performance.

---

### 4. Outlet Size Analysis

**Visualization:** Donut Chart

Total sales are compared across different outlet sizes:

* Small
* Medium
* High

The dashboard helps identify how outlet scale relates to overall revenue generation.

---

### 5. Outlet Location Analysis

**Visualization:** Funnel Chart

Sales are analyzed across:

* Tier 1
* Tier 2
* Tier 3

Current dashboard results show:

| Location Tier |  Total Sales |
| ------------- | -----------: |
| **Tier 3**    | **$299.37K** |
| **Tier 1**    | **$130.48K** |
| **Tier 2**    |  **$78.05K** |

Tier 3 locations are the strongest sales contributors in this dataset.

---

### 6. Outlet Type Analysis

**Visualization:** Table

The dashboard compares sales, item volume, and ratings across outlet types.

| Outlet Type        |    Sales | Items | Avg Rating |
| ------------------ | -------: | ----: | ---------: |
| Grocery Store      |  $37.18K |   265 |       ~4.0 |
| Supermarket Type 1 | $208.53K | 1,503 |       ~4.0 |
| Supermarket Type 2 | $131.48K |   928 |       ~4.0 |
| Supermarket Type 3 | $130.71K |   935 |       ~4.0 |

**Supermarket Type 1** is the strongest-performing outlet type in terms of both sales and item volume.

---

## 🎛️ Interactive Features

The dashboard includes interactive slicers that allow users to dynamically filter the analysis.

### Available Filters

* **Outlet Location Type**
* **Outlet Size**
* **Item Type**

Users can combine filters to drill down into specific products, locations, and outlet segments.

---

## 💡 Key Business Insights

### 1. Tier 3 outlets lead overall sales

Tier 3 outlets generate approximately **$299.37K**, significantly higher than Tier 1 and Tier 2 outlets in this dataset.

This suggests that the highest revenue contribution does not necessarily come from the locations that might traditionally be expected to have the largest urban markets.

---

### 2. Supermarket Type 1 is the strongest outlet type

Supermarket Type 1 generates approximately **$208.53K** in sales and accounts for **1,503 items**, making it the largest contributor among the outlet types analyzed.

---

### 3. Older outlets show stronger sales performance

Outlets established around **2012 or earlier** show considerably higher sales than many newer outlets.

This may indicate differences in:

* Outlet maturity
* Customer base
* Location
* Outlet size
* Product availability
* Operational scale

Further analysis would be required before concluding that outlet age itself causes higher sales.

---

### 4. Customer ratings are relatively consistent

Average ratings remain close to **4.0** across most outlet and product segments.

This suggests that customer rating does not provide a strong differentiating factor in this dataset compared with sales, outlet type, or location.

---

### 5. Product categorization requires data standardization

The inconsistent `Item Fat Content` labels demonstrate an important data-quality issue.

Standardizing these values before visualization is necessary to ensure that categories such as `LF`, `Low Fat`, and `low fat` are not treated as separate groups.

---

## 🧱 Data Model

The project primarily uses the following tables:

### `BlinkIT Grocery Data`

The main fact table containing:

* Product attributes
* Outlet attributes
* Sales
* Ratings
* Visibility
* Establishment information

### `Matrix`

A disconnected **field parameter table** used to control the metric displayed in the Fat Content visual.

The parameter enables users to switch between:

* Average Sales
* Number of Items
* Average Rating
* Total Sales

No relationship is required between the `Matrix` table and the main dataset because it functions as a field parameter rather than a traditional dimension table.

---

## 🛠️ Tools & Technologies

| Tool                        | Purpose                          |
| --------------------------- | -------------------------------- |
| **Microsoft Excel**         | Source dataset                   |
| **Power Query**             | Data cleaning and transformation |
| **Power BI Desktop**        | Dashboard development            |
| **DAX**                     | Measures and KPI calculations    |
| **Power BI Visualizations** | Data storytelling and analysis   |

---

## 📁 Repository Structure

```text
blinkit-sales-outlet-performance/
│
├── README.md
│
├── data/
│   └── BlinkIT_Grocery_Data.xlsx
│
├── dashboard/
│   └── BlinkIT_Sales_Dashboard.pbix
│
├── screenshots/
│   ├── dashboard_overview.png
│   ├── fat_content_analysis.png
│   ├── item_type_analysis.png
│   ├── outlet_establishment_analysis.png
│   ├── outlet_size_analysis.png
│   └── outlet_type_analysis.png
│
└── documentation/
    └── business_requirements.md
```

---

## 🚀 How to Explore the Project

### Option 1 — View the Dashboard

Open the dashboard screenshots available in the `screenshots/` directory.

### Option 2 — Open the Power BI File

1. Install **Power BI Desktop**.
2. Clone or download this repository.
3. Open:

```text
dashboard/BlinkIT_Sales_Dashboard.pbix
```

4. If the dataset path needs to be updated, open **Power Query** and point the source to:

```text
data/BlinkIT_Grocery_Data.xlsx
```

5. Refresh the dataset.
6. Explore the dashboard using the interactive filters.

---

## 📌 Project Outcomes

Through this project, I gained practical experience in:

* Data cleaning and transformation
* Power Query
* DAX measure creation
* KPI development
* Data modeling
* Field parameters
* Interactive slicers
* Power BI visualization
* Business-oriented data analysis
* Identifying data-quality issues
* Converting raw data into actionable insights

---

## 🔍 Skills Demonstrated

**Data Analytics**

`Excel` · `Power Query` · `Power BI` · `DAX` · `Data Cleaning` · `Data Visualization` · `Business Intelligence`

**Analytical Skills**

`KPI Development` · `Trend Analysis` · `Segmentation` · `Business Insights` · `Data Quality Analysis`

---

## 👩‍💻 Author

**Nitu**

BCA Student | Aspiring Data Analyst

**Interests:** Data Analytics · Business Intelligence · Power BI · Excel · Python · AI

---

⭐ If you found this project useful, feel free to explore the repository and dashboard files.
