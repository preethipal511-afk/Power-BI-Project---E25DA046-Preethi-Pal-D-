# Week 8: Student Performance Power BI Dashboard

## 📌 Project Overview
This project presents an interactive **Student Performance Dashboard** built in Power BI. The dashboard enables educators and administrators to evaluate key demographic factors, parental education levels, and test preparation impacts on academic scores (Math, Reading, and Writing) and overall pass rates.

---

## 📊 Key Features & Visuals

### 1. Main Overview Dashboard (`Page 1`)
* **KPI Summary Cards:** Quick view of overall metrics including average scores across subjects and overall pass percentages.
* **Interactive Slicers:** Filter data dynamically by Gender, Race/Ethnicity, Lunch Type, and Test Preparation Course status.
* **Demographic & Score Analysis:** Detailed breakdowns using bar, column, and donut charts to compare student groups.

### 2. Academic Profile (Drill-Through Page)
* **Targeted Analysis:** Allows granular examination of specific student segments (e.g., filtering by Gender).
* **Subject Score Pie Chart:** Displays score distribution across Math, Reading, Writing, and overall Pass Rate.
* **Score Comparison Ribbon Chart:** visualizes subject-wise score trends grouped by demographic categories.
* **Lunch Impact Waterfall Chart:** Evaluates score variations across free/reduced vs. standard lunch programs.
* **Key KPI Display:** Highlights specific subject metrics like `Math Avg`.

---

## 🛠️ Data & Measures (DAX)
Key calculated DAX measures implemented in this report:
* **Average Math Score:** `AVERAGE(StudentsPerformance[Math Score])`
* **Average Reading Score:** `AVERAGE(StudentsPerformance[Reading Score])`
* **Average Writing Score:** `AVERAGE(StudentsPerformance[Writing Score])`
* **Overall Average Score:** Average across all three core subjects.
* **Overall Pass %:** Calculated percentage of students achieving passing criteria.

---

## 📁 Repository Structure
