# 📝 NYC Schools Analysis – Database Population  

---

## 📝 Overview

This project focused on preparing, cleaning, and integrating NYC SAT results data into a **PostgreSQL database**.
The objective was to practice **ETL (Extract, Transform, Load)** workflows — from raw CSV preprocessing in Python to structured storage in a relational database — while following best practices in version control using Git and GitHub.

---

## ⚙️ Workflow Summary- Environment & Setup

1. Cloned the Git repository locally and opened it in **VS Code**.
2. Created a new feature branch for this task.
3. Used **Jupyter Notebook** to inspect, clean, and prepare the dataset for database population.
4. Established a connection between **Python** and **PostgreSQL** using **SQLAlchemy** and **psycopg2**.

---

## 🧹 Data Cleaning and Feature Engineering Logic

The cleaning process ensured data integrity, consistency, and readiness for relational storage.

| **Cleaning Step**        | **Action Taken**                                                                                                                   | **Rationale**                                                            |
| :----------------------- | :--------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------- |
| **Column Selection**     | Dropped irrelevant or duplicate columns (e.g., `SAT Critical Readng Avg. Score`, `internal_school_id`, `contact_extension`).       | Streamlined the dataset to retain only useful fields.                    |
| **Name Standardization** | Converted column names to **snake_case** and removed special characters.                                                           | Ensures consistent schema and compatibility with SQL naming conventions. |
| **Data Validation**      | Removed **duplicate rows** and enforced **unique DBN values**.                                                                     | Guarantees data integrity and a valid primary key structure.             |
| **Score Validation**     | Validated SAT section scores to fall within the **200–800 range**, setting invalid entries to **NULL**.                            | Maintains accuracy based on official SAT scoring rules.                  |
| **Percentage Cleaning**  | Removed `%` symbols, converted text to numeric values, and validated the **0–100 range**.                                          | Prepares percentage data for `DECIMAL` SQL fields.                       |
| **Feature Creation**     | Computed a new column `sat_total_score`. If all component scores were missing, the total was explicitly set to **NULL (`pd.NA`)**. | Creates a core analysis metric while avoiding misleading zero totals.    |

---

## 💻 Git Workflow

1. Committed and pushed cleaned data and scripts to a feature branch.
2. Published the branch to GitHub with a detailed commit message.
3. Created and submitted a **Pull Request (PR)** for review and merge.
4. Ensured version tracking, reproducibility, and team collaboration.

---

## 🚩 Challenges Encountered

* **Tool Integration:** Initial difficulty configuring **Python–PostgreSQL** connections using `SQLAlchemy` and `psycopg2`.
* **NULL Handling:** Ensuring Pandas’ `pd.NA` correctly translated to SQL `NULL` in numeric columns.
* **Environment Setup:** Managing dependencies and PostgreSQL connection strings in VS Code.

---

## 🧰 Tools & Libraries Used

* **Python** – for cleaning and preprocessing
* **Pandas** – for data manipulation and validation
* **SQLAlchemy / psycopg2** – for database integration
* **PostgreSQL** – as the target relational database
* **VS Code + Jupyter Notebook** – for analysis and execution
* **Git & GitHub** – for version control and collaboration

---

## 🚀 Skills Practiced

* Implementing **ETL workflows** using Python
* Performing **data validation, cleaning, and transformation**
* Managing **Git branches, commits, and pull requests**
* Working with **SQL-compatible data pipelines**
* Maintaining **data integrity and reproducibility** across systems

---

**✅ Summary:**
This project demonstrates a complete **data engineering workflow** — from raw SAT data to a clean, validated, and relationally stored dataset. The process reinforced critical skills in **data cleaning, schema design, and Git-based collaboration**, laying the groundwork for scalable data analysis in education systems.

---

### 🔗 [Back to Main Project README](https://github.com/Onyi-RICH/nyc-schools-analysis)

