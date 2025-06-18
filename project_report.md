# Access to Drinking Water Analysis

## 📘 Overview
This project investigates access to safe and affordable drinking water, focusing on inequalities in service levels between different countries and regions. The analysis aligns with the United Nations Sustainable Development Goal 6: *"Ensure availability and sustainable management of water and sanitation for all."*

The project utilizes data from the **WHO/UNICEF Joint Monitoring Programme (JMP)**, specifically the 2020 dataset, to explore key trends and relationships in access to drinking water.

---

## 📊 Data Description

- **Source:** WHO/UNICEF JMP – *Estimates on the use of water (2020)*
- **Format:** Originally CSV, processed in Google Sheets
- **Deliverable:** project_report ([Final Google Sheets File](https://docs.google.com/spreadsheets/d/1L31qBSQoGD8xnodihc3RH6xkvQ-szZt9TUIF7WrFdCY/edit?usp=sharing))
- <a href="https://docs.google.com/spreadsheets/d/1L31qBSQoGD8xnodihc3RH6xkvQ-szZt9TUIF7WrFdCY/edit?usp=sharing" target="_blank">Final Google Sheets File</a>


### Key Features:
- `name`: Country or area
- `income_group`: Income classification
- `pop_n`: National population (in thousands)
- `pop_u`: Urban population share (%)
- **Service Level Features:** Represent access levels across national (`_n`), rural (`_r`), and urban (`_u`) areas:
  - `wat_safe`: Safely managed
  - `wat_bas`: Basic
  - `wat_lim`: Limited
  - `wat_unimp`: Unimproved
  - `wat_sur`: Surface water

---

## ❓ Problem Statement
This project aims to:
- Identify global inequalities in water service access
- Compare population distributions and access levels across urban/rural areas
- Analyze trends by income group and population size
- Explore links between urbanization, income level, and water access

---

## 🛠️ Tools & Technologies Used

- **Google Sheets**: Data cleaning, transformation, EDA, visualizations  
  - Functions used: `COUNTA()`, `IFERROR()`, `ROUNDUP()`, `ABS()`, `AVERAGE()`, `MEDIAN()`, `MODE()`, `MIN()`, `MAX()`, `QUARTILE()`, `STDEV()`, `SUM()`
  - Logic: `IF`, `IFS`, `SWITCH`, `AND`, `OR`
  - Features: Pivot Tables, Split text to columns

- **GitHub**: Version control and project documentation

---

## 🔍 Key Steps Taken

### 1. Data Import & Cleaning
- Imported CSV into Google Sheets
- Handled delimiter issues (`;`)
- Fixed malformed rows with `COUNTA()` and manual corrections

### 2. Population Analysis
- Compared dataset totals with global 2020 estimates (7.821B, 55% urban)
- Calculated rural share (`pop_r`) = 100% - `pop_u`
- Created `pop_n (m)` to handle outliers visually

### 3. Access Level Analysis
- Cleaned access-level values (e.g. capped `wat_bas_n` at 100%)
- Calculated central tendencies (mean, median, mode) and spread (IQR, std dev)
- Extended analysis to urban and rural breakdowns

### 4. Relationship Analysis
- Created 100% stacked charts for access levels across:
  - National population
  - Urban population share
  - Rural population share

### 5. Income Group Analysis
- Generated pivot tables grouped by income level
- Converted income groups into numeric categories for sorting
- Visualized trends across income categories

---

## 📈 Insights & Findings

- The dataset is representative: e.g., only 1.70% difference in urban population vs. global estimates
- Urban vs. rural shares average around 50%
- `wat_bas_n` (national basic access) closely mirrors `wat_bas_u` (urban)
- IQR for rural surface water (`wat_sur_r`) is **~1.88**
- Higher urban population correlates with better access to basic water
- Some countries achieve 100% rural basic service, regardless of population share
- In low-income countries, avg. access to limited services is **~16.85%**
- Income group patterns:
  - Lower-middle-income countries have the most people
  - High-income nations are the most urbanized
  - GNI ↑ → Urbanization ↑, while unimproved/surface water access ↓

---

## ⚠️ Challenges & Lessons Learned

- **Data Quality Issues**: Delimiters, out-of-bounds values, missing data (`NAN`)
- **Error Handling**: `IFERROR()` helped resolve `#VALUE!` issues
- **Outliers**: Handled via unit conversion and aggregation
- **Visualization**: Simplified charts using rounded values and sorting
- **Contextual Awareness**: Relevance of MAE, MSE, RMSE even outside modeling
- **Data Integrity**: Emphasis on accurate structure and validation
- **Statistics Insight**: Trade-offs between Type I/II errors, model bias and variance
- **Ethics & Governance**: Importance of privacy, responsibility, and data trustworthiness

---

## 📊 Visuals (Created in Google Sheets)

- **Line Chart:** National vs. urban/rural population shares
- **Box & Whisker Plots:** Distribution of water access levels
- **100% Stacked Column Charts:** Composition by population type
- **Income Group Summary Chart:** Income group vs. access levels

---

## 💡 Final Reflection

This project highlights the end-to-end data analysis process — from cleaning and structuring to insight extraction — while reinforcing data ethics and the importance of data-driven decisions. With careful preprocessing, thoughtful statistics, and responsible interpretation, raw data becomes a tool for global impact.


