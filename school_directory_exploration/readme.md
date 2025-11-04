# 🏙️ NYC High Schools Analysis – School Directory Exploration  

**File:** `high-school-directory.csv`  
**Tool:** Python (VS Code Jupyter Notebook)  

---

## 📘 Overview  
This task focused on exploring and cleaning the **NYC High School Directory dataset** using **Python** and **Pandas** in a **Jupyter Notebook** within **VS Code**.  

The objective was to practice working with data locally, perform data exploration and cleaning, and generate insights using Python functions and visualizations.

---

## ⚙️ Setup  
As part of this task, I:  
- Configured **VS Code** to run **Jupyter Notebooks** locally.  
- Ensured that the **Python environment** and required libraries (like `pandas` and `matplotlib`) were properly installed.  

---

## 🔍 Data Exploration  
After loading the dataset into a Pandas DataFrame, I explored its structure and contents using the following methods:  

```python
df.head()       # Display first 5 rows
df.describe()   # Show summary statistics
df.info()       # Display column data types and count null values
```
These steps provided an overview of the dataset and helped identify missing values and inconsistent column names.

---

## 🧹 Data Cleaning  
To ensure consistency, I cleaned the column names by:  
- Using `.strip()` to remove extra whitespace  
- Using `.replace()` to replace spaces with underscores (`_`)  
- Applying a **regex pattern** to remove any special characters  

This standardization made the DataFrame easier to work with during analysis.  

---

## 📊 Data Analysis  

### Filtering for Brooklyn  
I filtered the dataset to include only schools located in **Brooklyn**, then answered the following:  

| Question | Answer |
|-----------|---------|
| **How many unique schools are in Brooklyn?** | 121 |
| **How many Brooklyn schools serve Grade 9?** | 121 |

---

### Grouping and Aggregation  
Used **`groupby()`** and **`nunique()`** to group and summarize data — counting unique values by borough.  
Also performed aggregations using:  

```python
df.groupby('borough').mean()
df.groupby('borough').describe()
```

---

### 📈 Visualization
Created a bar chart using Matplotlib to visualize the number of unique schools per borough

```python
import matplotlib.pyplot as plt
total_schools_per_borough = df.groupby('borough')['dbn'].nunique()
ax = total_schools_per_borough.plot(kind='bar', color='orange', figsize=(8, 6))

# Add titles and labels
ax.set_title('Number of Schools per Borough', fontsize=16)
ax.set_xlabel('Borough', fontsize=14)
ax.set_ylabel('Number of Schools', fontsize=14)
plt.xticks(rotation=45)

# Add the values for each bar
for i, value in enumerate(total_schools_per_borough):
    ax.text(i, value + 1, str(value), ha='center', fontsize=12)

plt.show()
```
---
### 🧰 Tools & Libraries Used

- **Python**
- **Pandas** – data exploration, cleaning, and grouping
- **Matplotlib** – data visualization
- **VS Code + Jupyter Notebook** – development environment

---
### 🚀 Skills Practiced

- Setting up and running **Jupyter notebooks** locally
- Data cleaning and transformation with **Pandas**
- Summarizing and grouping data
- Creating visualizations using **Matplotlib**

---

### 🔗 [Back to Main Project README](https://github.com/Onyi-RICH/nyc-schools-analysis)
