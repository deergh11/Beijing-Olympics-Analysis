# 🥇 Beijing 2022 Winter Olympics — End-to-End Azure Analytics Pipeline  
### *Azure Data Factory · Azure Databricks · Azure Synapse · ADLS Gen2 · Power BI*

---

## 📌 Project Overview

This project is a complete **end-to-end cloud data engineering and business intelligence pipeline**, built using the following Azure services:

- **Azure Blob Storage (Data Lake Storage Gen2)** — raw and transformed data storage  
- **Azure Data Factory (ADF)** — pipeline orchestration and ETL movement  
- **Azure Databricks** — PySpark-based data cleaning and transformation  
- **Azure Synapse Analytics (Serverless SQL)** — analytics modeling layer and SQL views  
- **Power BI Desktop** — final reporting and dashboard visualizations  

The solution processes real Olympic data from the **Beijing 2022 Winter Games**, transforming raw CSVs into analytical insights and interactive dashboards.  
It follows modern data engineering best practices by separating raw, transformed, and gold/semantic layers, and by using scalable compute for transformation and serverless SQL for BI.

---

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

<img width="1863" height="893" alt="image" src="https://github.com/user-attachments/assets/27109c13-91c5-48f2-b50a-cc162ba74cb6" />


Key operations performed:

- Standardized country names (e.g., *People’s Republic of China* → *China*)
- Normalized text casing (first letter uppercase)
- Removed nulls & duplicates
- Validated row counts
- Created harmonized fields for analytics
- Exported cleaned tables into Synapse Lake Database

---

## 🧠 Azure Synapse Analytics Layer (SQL Views)

<img width="1329" height="850" alt="image" src="https://github.com/user-attachments/assets/7f0a4a6a-2378-424f-b5bd-a6f42bbdde8f" />


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

<img width="1340" height="753" alt="image" src="https://github.com/user-attachments/assets/a341160d-4093-4b9a-aa90-800acb9f9f80" />

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

<img width="1338" height="751" alt="image" src="https://github.com/user-attachments/assets/08280456-5dfb-4544-82a4-1474db16b9f0" />


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

<img width="1334" height="744" alt="image" src="https://github.com/user-attachments/assets/4da2332f-dfae-4cfb-b32e-bf34683fc6de" />


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

<img width="1338" height="751" alt="image" src="https://github.com/user-attachments/assets/8b76f79a-6221-459a-82c1-a0a5b3cd3281" />


**Questions answered:**  
- Which countries specialize in which sports?  
- Which disciplines are deepest competitively?

---

## 🧩 Skills Demonstrated

### **Data Engineering**
- Designed cloud-based ETL pipelines using **Azure Data Factory**
- Ingested and organized datasets in **Azure Blob Storage (ADLS Gen2)**
- Performed large-scale cleaning, normalization, and transformation using **PySpark in Azure Databricks**
- Applied schema validation, column standardization, and data quality checks
- Built **analytics-ready SQL views** in Synapse for BI consumption

### **Business Intelligence**
- Wrote advanced SQL using CTEs, joins, ranking functions, and window functions
- Built derived metrics (dominance scores, efficiency ratios, gender parity KPIs)
- Designed a multi-page **Power BI executive dashboard**
- Translated raw data into clear stories and actionable insights

### **Cloud Technologies**
- **Azure Blob Storage (ADLS Gen2)** for raw & transformed data layers  
- **Azure Data Factory** for orchestration and data movement  
- **Azure Databricks** for PySpark transformations  
- **Azure Synapse (Serverless SQL)** for modeling and consumption views  
- **Power BI Desktop** for visualization and reporting  

---


## 📈 Key Insights

- Weighted medal scoring reveals *different* dominance than raw totals  
- Some nations achieve very high medal efficiency with small delegations  
- Coaching depth significantly correlates with medal production  
- Certain disciplines show near gender parity; others remain male-heavy  
- Team sports participation shows clear national specialization  
- Countries like Norway dominate gold-heavy sports due to specialization

---

## ⭐ Final Notes

This project demonstrates a complete **analytics engineering** workflow:

- Raw ingestion  
- Cloud-based transformation  
- SQL semantic modeling  
- Enterprise-grade BI visualization

This was a fun project to work on ahead of the 2026 Milan Winter Olympics.



