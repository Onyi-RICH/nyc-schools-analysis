# 🧠 NYC Schools Analysis – Database Queries

**Objective:** Use Python and SQL together to explore real-world education data by querying these tables:

- `high_school_directory` – School names, locations, types, programs
- `school_demographics` – Enrollment data, ELL, FRPL, disabilities, etc.
- `school_safety_report` – Reported incidents by type and location.
---

## 📘 Overview

This analysis focused on connecting to a **PostgreSQL database** using **psycopg2** and performing exploratory queries within a **Jupyter Notebook** environment in VS Code.

The goal was to:

* Practice **database connectivity** and **SQL querying**
* Retrieve **school-level insights** from multiple tables
* Combine and analyze data to identify key patterns across boroughs

---

## ⚙️ Setup

1. Installed and configured **psycopg2** to connect to the database and explore tables.
2. Used **Python in VS Code** to execute SQL queries directly from a notebook.
3. Queried tables, joined datasets, and visualized patterns through aggregated metrics.

---

## 🧮 Key Questions & Analysis

The following analytical questions guided the exploration:

* **Q1:** How many schools are in each borough?
* **Q2:** What is the average percentage of English Language Learners (ELL) per borough?
* **Q3:** Using school demographics and high school directory data, which are the **top 3 schools in each borough** with the highest percentage of **special education (SPED)** students?

---

## 💡 Insights

### 1. Borough-Level School Distribution 🏙

* **Brooklyn** has the highest number of schools (**121**), followed by **The Bronx (118)** and **Manhattan (106)**.
* **Queens** has **80** schools, while **Staten Island** has only **10**.
* This reflects variations in **population density** and **urban distribution** across NYC.

---

### 2. English Language Learners (ELL) Data Inconsistency 🗣

* Two separate summaries of ELL percentages revealed inconsistencies:

  * **Answer 1 (borough = M):** 11.87% average
  * **Answer 2 (borough = Manhattan):** 7.57% average
* This suggests potential **data quality issues**, possibly due to:

  * Inconsistent borough coding (e.g., “M” vs. “Manhattan”)
  * Incomplete translation of borough abbreviations
* Cleaning and standardizing these identifiers is crucial for accurate borough-level analysis.

---

### 3. Special Education (SPED) Duplication Issue ♻️

* The same school, **East Side Community School (01M450)**, appeared multiple times with slightly different SPED percentages (28.8%, 27.7%, 26.7).
* This duplication may stem from:

  * Multiple years or grade-level records
  * Missing DISTINCT filtering in the SQL query
* Applying **`DISTINCT`** on school names or DBN identifiers and verifying **JOIN conditions** would resolve redundancy.

---

## 🔧 Overall Data Improvement Recommendations

* **Normalize identifiers:** Standardize borough codes (e.g., map “M” → “Manhattan”).
* **Ensure uniqueness:** Verify distinct school entries using **`DISTINCT dbn`**.
* **Clean duplicates:** Address repeated records across datasets (e.g., multi-year overlaps).
* **Validate metrics:** Double-check calculated averages for consistency across queries.

---

## 🧰 Tools & Libraries Used

* **Python** – for scripting and data handling
* **SQL** – for querying and aggregating data
* **psycopg2** – to connect and run queries from Python notebooks
* **VS Code + Jupyter Notebook** – for executing and documenting analysis

---

## 🚀 Skills Practiced

* Connecting to and querying a **PostgreSQL database**
* Writing and optimizing **SQL queries**
* Performing **joins**, **aggregations**, and **data cleaning**
* Integrating **Python and SQL** for end-to-end analysis and insights

---

**✅ Summary:**
This project demonstrates how combining **Python**, **SQL**, and **notebook-based analysis** enables efficient exploration of educational data. While NYC’s school data offers rich insights, data quality and normalization remain key challenges for deeper, borough-level accuracy.
 

---

### 🔗 [Back to Main Project README](https://github.com/Onyi-RICH/nyc-schools-analysis)
