# Massachusetts Hospital Dashboard

A one-page interactive Power BI dashboard analyzing hospital encounter, patient, procedure, and payer data across Massachusetts cities from 2012 to 2022.
## Dataset: Maven Analytics (https://mavenanalytics.io/data-playground/hospital-patient-records)
---

## Dashboard Preview

<img width="599" height="339" alt="image" src="https://github.com/user-attachments/assets/ca9e3d0b-8258-4250-b9a8-a0ec78f08916" />

---

## Project Objective

Built for hospital management audiences, this dashboard answers four core operational questions:

- How many patients and encounters are recorded?
- What is the median base cost per procedure?
- Which payers handle the most encounters and coverage?
- How does encounter volume and cost vary by encounter class?

---

## Key Insights

- **Emergency and urgent care** consistently carry the highest median base costs ($146 and $143 respectively), while outpatient and ambulatory encounters average $86
- **Medicare** leads in total payer coverage at $19M, followed by Medicaid at $8M
- **Medicare** also ranks #1 by encounter count (11.4K), with NO_INSURANCE as a notable #2 at 8.8K — a finding relevant to hospital financial planning
- **2014** was the peak encounter year across the dataset; **2022 data covers Q1 only** and should not be interpreted as a full-year decline

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Power BI Desktop | Dashboard development, data modeling, and visualization |
| DAX | Custom measures for KPIs, median calculations, and conditional formatting logic |
| Power BI Data Model | Table relationships across encounters, patients, payers, and procedures |

---

## Dataset

**Source:** Maven Analytics (https://mavenanalytics.io/data-playground/hospital-patient-records)

**Tables used:**

| Table | Key Fields |
|-------|-----------|
| `encounters` | encounter class, base cost, total claim cost, payer coverage, start/stop dates |
| `patients` | patient demographics, city, race, gender |
| `payers` | payer name, headquarter state |
| `procedures` | procedure code, description, base cost |

---

## 📐 DAX Measures

```dax
-- Encounter Count
Encounter Count = COUNTROWS(encounters)

-- Patient Count
Patient Count = DISTINCTCOUNT(encounters[PATIENT])

-- Procedure Encounter Count
Procedure Encounter Count = COUNTROWS(procedures)

-- Procedure Median Base Cost
Procedure Median Base Cost = MEDIAN(procedures[BASE_COST])

-- Encounter Median Base Cost
Encounter Median Base Cost = MEDIAN(encounters[BASE_ENCOUNTER_COST])
```

---

## 📈 Visuals Included

- **KPI Cards** — Encounter Count, Patient Count, Procedure Encounter Count, Procedure Median Base Cost
- **Bar + Line Combo Chart** — Encounter and patient trend over the years (dual axis, 2012–2022)
- **Horizontal Bar Chart** — Median base cost by encounter class
- **Horizontal Bar Chart** — Top payers by payer coverage
- **Horizontal Bar Chart** — Top payers by encounter count
- **Horizontal Bar Chart** — Median base cost by procedure description type
- **Slicer** — Filter by city with clear all functionality


---

## 🚀 How to Open

1. Download the `.pbix` file from this repository
2. Open with [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
3. Use the **Select City** slicer to filter by Massachusetts city

---

## 👤 Author

**Jayvee Lotino**  
Political Economy Graduate | Aspiring Data Analyst  
