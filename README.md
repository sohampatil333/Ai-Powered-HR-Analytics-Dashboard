# HR Analytics — Interactive Dashboard

**A lightweight, offline, web-based HR Analytics dashboard** built with HTML, CSS and JavaScript (Plotly.js). Upload a CSV from your local machine to generate KPIs, interactive filters, and six visualizations.

> 💡 *This project was ideated, designed, and developed using AI assistance (ChatGPT) to demonstrate how AI can accelerate data visualization and dashboard creation.*

---

## 🔎 Project overview

This repository contains a single-page, client-side dashboard that reads an HR CSV file in the browser and renders an interactive analytics experience. The dashboard was built to be portable — no server required — and is ideal for sharing as a portfolio project on GitHub.

Key features

* Upload CSV from local computer (no backend)
* Top KPI cards (Total employees, Attrition rate, Avg Monthly Income, Avg Job Satisfaction)
* Two slicers (Department, Gender) that update KPIs, charts and summary dynamically
* Six interactive Plotly visualizations:

  1. Attrition by Department (grouped bar)
  2. Monthly Income distribution by Job Role (boxplot)
  3. Attrition by Age Group & Gender (grouped bar)
  4. Job Satisfaction vs Work-Life Balance (heatmap)
  5. Overtime & Attrition breakdown (sunburst / donut style)
  6. Attrition by Education Field (bar)
* Dynamic text summary that updates with filters
* Clean responsive UI (CSS Grid / Flexbox)

> ⚠️ This project uses Plotly.js via CDN and PapaParse (for CSV parsing). It works fully offline once you open the HTML file from your filesystem.

---



## ✅ How to use (for non-technical users)

1. Clone or download this repository to your computer.
2. Open `HR_Analytics_Dashboard_v2.html` in your web browser (Chrome / Edge / Firefox recommended).
3. Click the **Upload CSV** control in the top-right area and select your HR dataset (CSV).
4. Use the **Department** and **Gender** filters to slice the data — the KPI cards, charts, and summary will update instantly.

> Tip: If a chart shows `No data`, check the CSV column names and make sure they match expected headers listed below.

---

## 🧾 Expected CSV format (column headers)

The dashboard expects the CSV to contain (at minimum) the following columns. Column names are case-sensitive in the HTML code — use these exact headers or edit the HTML to match your column names.

```
EmpID,Age,AgeGroup,Attrition,BusinessTravel,DailyRate,Department,DistanceFromHome,Education,EducationField,EmployeeCount,EmployeeNumber,EnvironmentSatisfaction,Gender,HourlyRate,JobInvolvement,JobLevel,JobRole,JobSatisfaction,MaritalStatus,MonthlyIncome,SalarySlab,MonthlyRate,NumCompaniesWorked,Over18,OverTime,PercentSalaryHike,PerformanceRating,RelationshipSatisfaction,StandardHours,StockOptionLevel,TotalWorkingYears,TrainingTimesLastYear,WorkLifeBalance,YearsAtCompany,YearsInCurrentRole,YearsSinceLastPromotion,YearsWithCurrManager
```

### Minimal required fields for full functionality

* `Attrition` (values like `Yes` / `No`)
* `Department`
* `JobRole`
* `MonthlyIncome` (numeric)
* `AgeGroup` (e.g., `18-25`, `26-35`)
* `Gender` (e.g., `Male`, `Female`)
* `JobSatisfaction` (1–4)
* `WorkLifeBalance` (1–4)
* `OverTime` (Yes/No)
* `EducationField`

If your dataset uses different column names, either rename columns in your CSV or edit the variable mapping in the HTML file.

---

## 🛠 Technical details

* Charts: Plotly.js (CDN `https://cdn.plot.ly/plotly-latest.min.js`)
* CSV parsing: PapaParse (CDN)
* Implementation: Vanilla JavaScript (ES6), HTML5, CSS (Grid + Flexbox)
* No build tools, no server — single HTML file

---

## 🔧 Customization (quick pointers)

* To change which columns the dashboard reads, open `HR_Analytics_Dashboard_v2.html` and search for the top-level variable names such as `d['Attrition']`, `d['Department']`, `d['MonthlyIncome']` and update them to your CSV headers.
* To add/remove KPIs, modify the `computeKPIs()` function inside the script and update the DOM elements showing KPI values.
* To change chart styles or colors, look for Plotly trace definitions and update marker or layout options.

---


## 📝 Example (sample row)

```
EmpID,Age,AgeGroup,Attrition,Department,JobRole,MonthlyIncome,Gender,JobSatisfaction,WorkLifeBalance,OverTime,EducationField
RM297,28,26-35,Yes,Research & Development,Laboratory Technician,1420,Male,3,3,No,Life Sciences
```

---



## 🤖 Built with AI Assistance

This dashboard was created in collaboration with **AI (ChatGPT)**. The AI assisted in designing the layout, writing and optimizing the JavaScript code, and structuring the visualizations using Plotly.js. The goal was to demonstrate how modern AI tools can significantly enhance productivity in data analysis and visualization projects.

---

## 🧾 About this project

This dashboard and the HTML/CSS/JS code were developed with the assistance of AI tools to accelerate development and help with code generation and optimization.

---
