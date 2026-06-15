# HR Employee Performance Analysis Dashboard
### Power BI Mini Project – README

---

## 📁 Project Overview

This project analyses HR employee performance data using **Excel** (data cleaning) and **Power BI** (dashboard & visualisation). The goal is to help HR teams make data-driven decisions on performance, retention, and workforce management.

---

## 📄 Files Included

| File | Description |
|------|-------------|
| `HR_Performance_Report_Template.docx` | Full project report in template format |
| `Mini_project.pdf` | Original Power BI dashboard screenshots & reference |

---

## 🗂️ Dataset Columns

| Column | Type | Description |
|--------|------|-------------|
| Employee_ID | String | Unique employee identifier |
| Department | Categorical | Finance / IT / Marketing / Sales / HR |
| Experience_Years | Integer | Years of work experience |
| Monthly_Salary | Float | Gross monthly salary (INR) |
| Attendance_Percentage | Float | Attendance rate (%) |
| Performance_Score | Float | Rating on 1–5 scale |
| Training_Hours | Integer | Training hours attended |
| Satisfaction_Score | Integer | Satisfaction score (1–10) |
| Overtime_Hours | Integer | Monthly overtime hours |
| Work_Mode | Categorical | WFH / Hybrid / Office |
| Attrition_Status | Boolean | Yes = Left / No = Stayed |
| Performance_Category | Categorical | Derived via DAX: High / Medium / Low |

---

## 🛠️ Tools & Technologies

- **Microsoft Excel** – Data cleaning, duplicate removal, missing value handling, conditional formatting
- **Power BI Desktop** – Data modelling, DAX measures, interactive dashboard

---

## 🧹 Data Cleaning Steps

1. Checked and handled **missing values**
2. Validated **data types** for all columns
3. Removed **duplicate rows**
4. Removed **unwanted columns**
5. Flagged **salary outliers** (> ₹1,00,000) using conditional formatting
6. Standardised text **formatting** across all fields

---

## 📊 DAX Measures Used

```dax
-- Performance Category (Derived Column)
Performance Category =
IF([Performance_Score] >= 4.0, "High",
   IF([Performance_Score] >= 2.5, "Medium", "Low"))

-- Total Employees
Total Employees = COUNT(Employee[Employee_ID])

-- Average Salary
Avg Salary = AVERAGE(Employee[Monthly_Salary])

-- Average Performance Score
Avg Performance = AVERAGE(Employee[Performance_Score])

-- Attrition Rate %
Attrition Rate =
DIVIDE(
  COUNTROWS(FILTER(Employee, Employee[Attrition_Status] = "Yes")),
  COUNT(Employee[Employee_ID])
) * 100
```

---

## 📈 Dashboard Visuals

1. **KPI Cards** – Total Employees, Avg Salary, Avg Performance Score
2. **Bar Chart** – Department-wise Average Salary
3. **Bar Chart** – Department-wise Average Performance Score
4. **Pie Chart** – Attrition Distribution (Stayed vs Left)
5. **Donut Chart** – Work Mode Distribution (WFH / Hybrid / Office)
6. **Scatter Plot** – Attendance % vs Performance Score

> Dashboard includes Drill-down, Slicers, Bookmarks, and Labels throughout.

---

## 💡 Key Insights

| Type | Insight |
|------|---------|
| **Descriptive** | IT & Finance have highest salaries; ~30% employees are High performers |
| **Diagnosis** | Low performers have fewer training hours and lower attendance |
| **Predictive** | Low satisfaction + high overtime → higher attrition risk |
| **Prescriptive** | Increase training for low performers; monitor overtime; improve work flexibility |

---

## ✅ How to Use the Report

1. Open `HR_Performance_Report_Template.docx` in Microsoft Word
2. Replace **SCREENSHOT OF DATA MODELLING** placeholder with your Power BI model screenshot
3. Replace **SCREENSHOT OF DASHBOARD / REPORT** placeholder with your dashboard screenshot
4. Submit!

---

*Project by: [Your Name] | Domain: HR Analytics | Tool: Power BI*
