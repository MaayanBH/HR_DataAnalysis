
# HR Data Analysis Workflow

Welcome to the HR Data Analysis project! This repository contains a robust workflow for performing in-depth human resources analytics using Python to assist HR teams and executives in making data-driven decisions.

---

## 1. Project Overview

This project aims to provide actionable insights into an organization's HR data, helping answer critical talent management questions such as:

- What are the key drivers of employee turnover?
- How do employee demographics relate to performance?
- Are there compensation gaps across departments or roles?
- Which factors contribute to absenteeism?

The core of the analysis is in [`python_data_project.ipynb`](notebooks/python_data_project.ipynb), which consolidates code, SQL extraction, and analytic findings. Data is sourced from HR-related tables (e.g., `table1`, `table2`, `hrtable1`, `hrtable2`), each offering unique dimensions into HR activities.

---

## 2. Data Description

**Datasets Loaded:**  
- `table1`: Employee master data (e.g., EmployeeID, Age, Department, Tenure, Gender)
- `table2`: Performance ratings, compensation details
- `hrtable1`: Absenteeism records
- `hrtable2`: Exit/turnover information

**Columns & Structure (example):**
| Table      | Columns                                                  | Purpose                           |
| ---------- | -------------------------------------------------------- | --------------------------------- |
| table1     | EmployeeID, Name, Age, Gender, Department, Tenure        | Demographics, Org Structure       |
| table2     | EmployeeID, PerformanceScore, BaseSalary, Bonus          | Performance, Compensation         |
| hrtable1   | EmployeeID, Date, AbsenceReason, Duration                | Absenteeism Analysis              |
| hrtable2   | EmployeeID, ExitDate, TerminationType, ExitReason        | Turnover Analysis                 |

**SQL Extraction:**  
The notebook establishes a connection to a MySQL database using `mysql-connector-python` to extract relevant data using SQL `SELECT` queries. Example:
```python
import mysql.connector
connection = mysql.connector.connect(host='...', user='...', db='...')
query = "SELECT * FROM table1"
df = pd.read_sql(query, connection)
```

---

## 3. Analysis Summary

The HR data analysis delivers insights in several dimensions:

- **Employee Performance:** Analyzes the distribution of performance scores and correlates them to factors like tenure and compensation.
- **Demographics:** Examines workforce composition across departments, age groups, and gender, identifying diversity patterns.
- **Compensation:** Assess pay distribution by role, tenure, or performance band, highlighting potential inequities.
- **Absenteeism:** Studies trends in employee absences, reasons, and duration to uncover organizational hotspots.
- **Turnover Probability:** Applies statistical analysis (correlation, regression) to flag attributes associated with higher likelihood of exit.

Key findings are visually explored with charts and tables, guiding recommendations for retention and workforce planning.

---

## 4. Workflow Explanation

Key Steps Implemented:

1. **SQL Connection & Extraction:**  
   Secure connection to the HR SQL database and efficient data retrieval via SQL queries.

2. **Data Cleaning:**  
   - Handling missing values (imputation, removal)
   - Standardizing/renaming columns for consistency
   - Removing duplicates and outliers

3. **DataFrames Creation & Merging:**  
   Transformation of SQL query outputs into pandas DataFrames. DataFrames are merged/joined on `EmployeeID` for holistic analysis.

4. **Analysis & Visualization:**  
   - Descriptive statistics (means, medians, counts)
   - Grouping and aggregating data by dimension (e.g., department, tenure)
   - Creating plots to communicate insights
   - Identifying trends (e.g., tenure vs. performance, gender pay gap)

---

## 5. Visuals / Example Plots

Below are sample visualizations generated (or suggested) in the notebook. Charts can be found in the `images/` directory or created by rerunning the notebook.

![Employee Distribution by Department](images/employee_distribution.png)

*Figure 1: Distribution of Employees Across Departments*

![Compensation Heatmap](images/compensation_heatmap.png)

*Figure 2: Correlation Heatmap of Compensation, Performance, and Tenure*

![Absenteeism by Reason](images/absenteeism_pie.png)

*Figure 3: Absenteeism Frequency by Reason*

![Performance vs Tenure](images/performance_vs_tenure.png)

*Figure 4: Scatter Plot of Performance Score vs. Tenure*

---

## 6. How to Run the Project

### Requirements

- **Python**: >=3.8 recommended
- **Libraries:**
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `seaborn`
  - `mysql-connector-python`
  - Optional: `jupyter`, `sqlalchemy`, `scikit-learn` (for advanced ML steps)

### Setup & Execution

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   ```

2. **Install Required Packages**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure SQL Connection**
   - Edit the connection settings in the first cell of the notebook (`python_data_project.ipynb`), e.g.:
     ```python
     connection = mysql.connector.connect(
         host='your_host',
         user='your_user',
         password='your_password',
         database='your_db'
     )
     ```

4. **Run the Notebook**
   ```bash
   jupyter notebook notebooks/python_data_project.ipynb
   ```

---

## 7. Repository Structure

```
/data                 # (Optional) Local copies of HR tables
/images               # Output plots and visualizations
/notebooks
    └── python_data_project.ipynb
/src                  # Custom Python modules and helpers
README.md
requirements.txt
```

---

## 8. Conclusion & Future Work

This repository provides a practical foundation for HR data analysis, identifying opportunities for organizational improvement. Next steps and potential enhancements include:

- **Predictive Modeling:** Develop models to forecast employee turnover and identify at-risk talent cohorts.
- **Interactive Dashboards:** Integrate results with PowerBI or Tableau for dynamic, real-time HR analytics.
- **Advanced ML Applications:** Explore clustering (segmentation), anomaly detection (fraud/absenteeism), or NLP on exit interviews.
- **Continuous Integration:** Automate data refresh and reporting pipelines for up-to-date workforce intelligence.

---

For more details, please review the annotated code and comprehensive analysis inside [`python_data_project.ipynb`](notebooks/python_data_project.ipynb).  
For questions or contributions, open an issue or PR on this repository.

---


