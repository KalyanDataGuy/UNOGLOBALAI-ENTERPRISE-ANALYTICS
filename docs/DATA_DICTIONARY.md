# DATA DICTIONARY — UNO GLOBAL AI
Enterprise Analytics & Decision Intelligence  
Author: KalyanDataGuy

This document defines **all 9 sheets** in the Uno Global AI master workbook.
The dataset is synthetic in source but business-realistic in behavior.

---

## 0. PROJECT_INFO_README (Author & IP Notice)

Grain: N/A (informational)

Uno Global AI — Enterprise Analytics & Decision Intelligence  
Author: KalyanDataGuy  
GitHub Portfolio Master Workbook (8 core sheets + 1 data model)

**IP & Usage Notice**
- This workbook is an original analytics project created by KalyanDataGuy.
- Allowed: viewing, interview discussion, and learning references.
- Not allowed: copying the data/model as your own work, reposting without attribution,
  or using this content in commercial client deliverables without written consent.
- If forked on GitHub, this notice and author name must remain intact.

**Note:**  
This workbook is designed for read-only portfolio review.  
For editable models or source logic, contact the author.

© 2025 | KalyanDataGuy | Uno Global AI — Enterprise Analytics

---

## 1. UGAI_Employees

Grain: 1 row = 1 employee  
Primary Key: EmployeeID  

Purpose:
Workforce composition, salary structure, performance tracking, attrition analysis.

Key Fields:
EmployeeID, Name, Gender, Country, Region, Location, Department, Designation,  
Primary_ReportingManager, Secondary_ReportingManager, HireDate, TenureYears,  
Emp_Age, SalaryUSD, Project, TechStack, Performance_Q1–Q4, PerformanceRating,  
ExitStatus, AttritionFlag, YearQuarter, ExitYearQuarter.

---

## 2. UGAI_Projects

Grain: 1 row = 1 project  
Primary Key: ProjectID  

Purpose:
Project portfolio management, ROI analysis, budget and ESG tracking.

Key Fields:
ProjectID, Project_Name, Project_Domain, Project_Region, Start_Date, End_Date,  
Project_Client, Project_Status, Budget_USD, ActualCost_USD, Profit_USD,  
ROI_Pct, ESG_ImpactScore, Project_Duration_Months.

---

## 3. UGAI_ProjectAllocation

Grain: Employee × Project × YearQuarter  
Primary Key: EmployeeID + ProjectID + YearQuarter  

Purpose:
Utilization, capacity planning, allocation-based cost modeling.

Key Fields:
EmployeeID, Employee_Name, Employee_Region, Role_Category, Department,  
Skill_Tech_Stack, ProjectID, Project_Name, Project_Domain, Project_Region,  
Allocation_Start_Date, Allocation_End_Date, Allocation_Months, Allocation_Pct,  
Allocation_Rationale, SalaryUSD, YearQuarter, AllocationSalaryCost_USD.

---

## 4. UGAI_Financials

Grain: Country × YearQuarter  
Primary Key: Country + YearQuarter  

Purpose:
Revenue, expense, profit and margin analysis by geography and time.

Key Fields:
Year, Quarter, YearQuarter, Country, RevenueUSD_New, ExpenseUSD_New,  
ProfitUSD_New, MarginPct_New, Headcount, AvgSalaryUSD, AvgPerformanceScore.

---

## 5. UGAI_Yearonyear

Grain: 1 row = 1 year  
Primary Key: Year  

Purpose:
Year-on-year trend analysis and executive storytelling.

Key Fields:
Year, Project_Start_Revenue_USD_Mn, Project_Start_Profit_USD_Mn,  
Active_Project_Count, Active_Revenue_USD_Mn, Active_Profit_USD_Mn,  
Business_Context_For_Year.

---

## 6. UGAI_Regionalanalytics

Grain: 1 row = 1 region  
Primary Key: Region  

Purpose:
Regional performance comparison and workforce health assessment.

Key Fields:
Region, Total_Employees, Avg_Performance_Rating,  
Total_Revenue_USD_Million, Total_Profit_USD_Million,  
Avg_Salary_USD_K, Attrition_Percent.

---

## 7. UGAI_Strategicevents

Grain: 1 row = 1 strategic event  
Primary Key: Year + Key_Milestone  

Purpose:
Connect strategic decisions with financial and workforce outcomes.

Key Fields:
Year, Quarter, Phase, Primary_Region, Key_Milestone,  
Strategic_Event, Description, Impact_Type, Impact_Score_1to5.

---

## 8. UGAI_ExecutiveDashboard

Grain: Pre-aggregated KPIs (summary layer)  
Primary Key: N/A  

Purpose:
CXO-level snapshot for executive decision-making.

Key Fields:
Metric, Value, Comparison, Trend, Commentary.

---

## 9. UGAI_Data_Model

Grain: N/A (documentation)

Purpose:
Logical and visual representation of entity relationships, grain, and join keys.

Notes:
- Employees ↔ ProjectAllocation ↔ Projects via EmployeeID and ProjectID
- Allocation ↔ Financials via YearQuarter
- Yearonyear ↔ Strategicevents via Year
- Country and Region enable geographic roll-ups

---

## Status

✅ All 9 sheets documented  
✅ Grain and keys clearly defined  
✅ GitHub-ready  
✅ Interview-ready
