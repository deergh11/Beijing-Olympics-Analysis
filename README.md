# 🥇 Beijing 2022 Winter Olympics — End-to-End Analytics Pipeline  
### *Azure Synapse Analytics · Spark · SQL · Power BI · Data Engineering + BI Project*

---

## 📌 Project Overview

This project is a complete **end-to-end data engineering and business intelligence pipeline** built using:

- **Azure Synapse Analytics** (Serverless SQL, Spark Pool, Lake Database)  
- **Azure Data Lake Storage Gen2**  
- **PySpark (Databricks-style transformations)**  
- **SQL Views for BI Consumption**  
- **Power BI Dashboard**

The goal is to take raw publicly available data from the **Beijing 2022 Winter Olympics**, clean it, model it, create analytical SQL views, and develop a **multi-page Power BI report** that tells meaningful stories about:

- Medal dominance  
- Delegation efficiency  
- Gender participation & parity  
- National specialization in team sports  

This project simulates a real-world **data engineering + BI workflow**, transforming raw data into actionable insights.

---


---

## 🗃️ Dataset Description

| Table | Columns | Description |
|--------|---------|-------------|
| **athletes** | Name, Country, Discipline | Olympic athletes & sports |
| **coaches** | Name, Country, Discipline | Coaching staff |
| **genders** | Discipline, Female, Male, Total | Gender participation |
| **medals** | Country, Gold, Silver, Bronze, Total | Medal standings |
| **teams** | Country, Discipline | Team event entries |

Datasets were cleaned and standardized using PySpark and loaded into Synapse.

---

## 🔄 Data Transformations (Spark)

Key operations performed:

- Standardized country names (e.g., *People’s Republic of China* → *China*)
- Normalized text casing (first letter uppercase)
- Removed nulls & duplicates
- Validated row counts
- Created harmonized fields for analytics
- Exported cleaned tables into Synapse Lake Database

---

## 🧠 Analytics Layer (SQL Views)

A dedicated SQL database (`OlympicsViewsDB`) was created to expose clean analytical views to Power BI.

### Medal Insights
- `v_MedalDominance`
- `v_MedalShareByCountry`

### Delegation & Efficiency
- `v_AthletesByCountry`
- `v_CoachesByCountry`
- `v_AthleteCoachRatio`
- `v_MedalsPerAthlete`

### Gender Analysis
- `v_GenderOverall`
- `v_GenderByDiscipline`

### Team & Discipline Strengths
- `v_TeamsByDiscipline`
- `v_TeamsByCountry`
- `v_TeamsByDisciplineCountry`
- `v_TopCountriesByDiscipline`

All view definitions are included in the `sql/create_views.sql` file.

---

## 📊 Power BI Dashboard

The project includes a **4-page Power BI dashboard**:

---

### 📌 Page 1 — Medal Performance  
**Visuals:**
- Medal dominance table  
- Total medal bar chart  
- Gold-only ranking  
- Weighted dominance scoring  

**Questions answered:**  
- Who dominated Beijing 2022?  
- How does total vs. gold performance compare?

---

### 📌 Page 2 — Delegations & Efficiency  
**Visuals:**
- Delegation size  
- Medals-per-athlete efficiency scatterplot  
- Coaching ratio (athletes per coach)  
- Coaches by country  

**Questions answered:**  
- Who overperformed with fewer athletes?  
- Does coaching depth drive performance?

---

### 📌 Page 3 — Gender Participation & Parity  
**Visuals:**
- Gender KPI cards  
- Female participation % by discipline  
- Male vs female counts per discipline  
- Overall gender split  

**Questions answered:**  
- Which sports approach gender parity?  
- What does overall participation look like?

---

### 📌 Page 4 — Teams & Disciplines  
**Visuals:**
- Team count by discipline  
- Team count by country  
- Heatmap (discipline × country)  
- Top 3 countries per discipline  

**Questions answered:**  
- Which countries specialize in which sports?  
- Which disciplines are deepest competitively?

---

## 🧩 Skills Demonstrated

### **Data Engineering**
- PySpark transformations  
- ADLS Gen2 ingestion  
- Schema design  
- Lake Database modeling  
- Serverless SQL view creation  

### **Business Intelligence**
- Analytical SQL (CTEs, window functions, ratios)  
- KPI development  
- Multi-page dashboard design  
- Storytelling with data  

### **Cloud Technologies**
- Azure Synapse Analytics  
- Spark Pools  
- Serverless SQL Pools  
- Power BI Desktop  

---

## 📈 Key Insights

- Weighted medal scoring reveals *different* dominance than raw totals  
- Some nations achieve very high medal efficiency with small delegations  
- Coaching depth significantly correlates with medal production  
- Certain disciplines show near gender parity; others remain male-heavy  
- Team sports participation shows clear national specialization  
- Countries like Norway dominate gold-heavy sports due to specialization

A full insight write-up is included in `documentation/insights_summary.md`.

---

## 🚀 How to Reproduce

1. Upload raw datasets to **Azure Data Lake Gen2**
2. Run PySpark transformations in Synapse
3. Create SQL views with `sql/create_views.sql`
4. Connect Power BI to:
5. Load all analytic views  
6. Open **BeijingOlympicsDashboard.pbix** to explore the final report

---

## ⭐ Final Notes

This project demonstrates a complete **analytics engineering** workflow:

- Raw ingestion  
- Cloud-based transformation  
- SQL semantic modeling  
- Enterprise-grade BI visualization  

It represents a comprehensive, real-world, cloud-driven data solution.




