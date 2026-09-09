# 📦 Logistics Data Collection, Cleaning & Preprocessing

## 🎯 Objective
This project focuses on identifying a real-world, publicly available logistics dataset and applying data cleaning and preprocessing techniques to make it analysis-ready. The goal is to demonstrate the importance of data integrity in logistics operations and decision-making.

## 📂 Data Source
**Dataset:** Smart Logistics Supply Chain Dataset
**Source:** Kaggle (Public Repository)
**Justification:** This dataset was selected because it contains real-world logistics data including shipment tracking, inventory levels, delivery delays, and IoT sensor readings (temperature, humidity, traffic conditions). It closely represents actual supply chain operations, making it suitable for practicing data cleaning techniques on realistic, messy data.

**Dataset Details:**
- Total Records: 1,000 rows
- Total Columns: 16
- Time Period: Year 2024
- Key Fields: Timestamp, Asset_ID, Latitude, Longitude, Inventory_Level, Shipment_Status, Temperature, Humidity, Traffic_Status, Waiting_Time, Logistics_Delay, Logistics_Delay_Reason

## 🧹 Data Cleaning Process

### 1️⃣ Initial Data Assessment
Before cleaning, the dataset was inspected for:
- Missing values across all columns
- Duplicate rows
- Data type consistency

### 2️⃣ Findings
- **Duplicate Rows:** 0 duplicates found — no removal needed.
- **Missing Values:** 263 missing values found in the `Logistics_Delay_Reason` column. All other columns had 0 missing values.
- **Data Types:** All columns had appropriate data types (numeric fields as int64/float64, categorical fields as object).

### 3️⃣ Handling Missing Values
The missing values in `Logistics_Delay_Reason` were investigated further. It was determined that these missing entries corresponded to shipments where no delay occurred — meaning a "reason" for delay would logically not exist.

**Action Taken:** Missing values in `Logistics_Delay_Reason` were filled with the label `"No Delay"` to accurately represent this scenario, rather than being dropped, since dropping these rows would have resulted in unnecessary loss of valid data (26.3% of the dataset).

### 4️⃣ Tools Used
- 🐍 **Python** (Pandas library) for data loading, inspection, and cleaning
- 📓 **Google Colab** as the development environment

## 📁 Files in This Repository
| File | Description |
|------|--------------|
| `smart_logistics_dataset.csv` | Original raw dataset (as downloaded from Kaggle) |
| `cleaned_smart_logistics_dataset.csv` | Final cleaned dataset, ready for analysis |

## ⚠️ Challenges Encountered
The main challenge was determining the correct approach for handling missing values in `Logistics_Delay_Reason`. Rather than applying a generic fix (such as dropping rows or filling with the mean/mode), the missing values were analyzed contextually and understood to represent "no delay occurred" — resulting in a more accurate and meaningful cleaning decision.

## 💡 Reflection: Importance of Data Quality in Logistics
Data quality directly impacts logistics decision-making. Missing or inconsistent data — such as unexplained delivery delays — can lead to inaccurate performance reporting and poor operational decisions (e.g., misallocating resources to routes that appear delay-free when data is simply missing). Proper preprocessing ensures that downstream analysis, such as identifying delay patterns or optimizing routes, is built on reliable, trustworthy data. This project reinforced that thorough data cleaning is not just a technical step, but a critical foundation for accurate business intelligence in supply chain operations.

---
**👤 Author:** Shahnawaz Khan
**📌 Task:** Week 1 - Virtual Logistics Data Analysis Internship
