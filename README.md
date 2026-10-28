# 🛡️ Insurance Policy & Claims Analysis — Power BI Dashboard

An interactive Power BI dashboard for **Prism Insurance Pvt. Ltd.** (a fictional company used for this project) that analyses policies, premiums, coverage and claims. The data is stored in **SQL Server** and visualised in **Power BI** so you can track how the business performs, which policy types bring in the most premium, and how claims are distributed across customers.

---

## 📌 Project Objectives

- Track headline KPIs: **Total Premium**, **Total Coverage** and **Total Claim Amount**
- Compare **premium collected by policy type**
- Monitor **claims by status** (e.g. approved, pending, rejected)
- Understand **claim amounts across age groups** and the **gender split** of customers
- See how many policies are **active vs inactive**
- Look up any individual **policy, claim or customer** in detail

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Microsoft SQL Server** (SSMS) | Creating the `Insurancedb` database and storing the `InsuranceData` table |
| **Power BI Desktop** | Data modelling, visuals and dashboard design |
| **Power Query** | Data cleaning and creating calculated columns (Age Groups, Active/Inactive status) |

---

## 📂 Repository Structure

```
├── Insurance_Report.pbix     # Power BI report (2 pages)
├── Insurance_SQL.sql         # SQL Server script to create the database and query the data
└── README.md
```

---

## 🗄️ SQL Server Setup

`Insurance_SQL.sql` creates the database and checks that the imported data is there:

```sql
CREATE DATABASE Insurancedb;

SELECT * FROM [dbo].[InsuranceData];
```

The insurance dataset is imported into the `dbo.InsuranceData` table, which Power BI uses as its data source.

---

## 🗃️ Dataset Fields

| Field | Description |
|-------|-------------|
| `PolicyNumber` | Unique policy identifier |
| `CustomerID` | Unique customer identifier |
| `ClaimNumber` | Unique claim identifier |
| `Gender` | Customer gender |
| `Age` | Customer age |
| `PolicyType` | Type of insurance policy |
| `PolicyStartDate` / `PolicyEndDate` | Policy validity period |
| `PremiumAmount` | Premium paid for the policy |
| `CoverageAmount` | Total coverage offered by the policy |
| `ClaimDate` | Date the claim was filed |
| `ClaimAmount` | Amount claimed |
| `ClaimStatus` | Current status of the claim |

**Calculated columns created in Power BI:**
- **Age Groups**: customers grouped into age bands
- **Active / Inactive**: policy status based on the policy start and end dates

---

## 📊 Dashboard Pages

### 1️⃣ Data Visualisation
The main dashboard with KPIs, charts and filters.
<img width="807" height="461" alt="image" src="https://github.com/user-attachments/assets/3ea7efb1-dd80-4d27-b0db-1475aada524b" />


**KPI cards**
- Total Premium Amount
- Total Coverage Amount
- Total Claim Amount
- Customer count by Gender

**Visuals**
- **Number of Claims by Claim Status** (ribbon chart)
- **Premium Amount by Policy Type** (bar chart)
- **Claim Amount by Age Groups** (line chart)
- **Count of Active / Inactive Policies** (donut chart)
- **Coverage Amount matrix** by Policy Type × Claim Status

**Slicers:** Policy Number, Claim Number, Customer ID. Pick any one to filter the whole page to that policy, claim or customer.

### 2️⃣ Data Table
A detailed record-level table with every policy and claim field, including age group and active/inactive status. A navigation button links back to the main dashboard.
<img width="802" height="462" alt="image" src="https://github.com/user-attachments/assets/cf753737-4a89-4b1d-9d89-f93186f063d6" />
