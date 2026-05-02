# 🏥 Hospital Emergency Room Dashboard
Hospital Emergency Room Dashboard Dashboard Link: https://drive.google.com/file/d/1FSFLLNrfonkT90yJbhzqDEa7ZKyJ7pTH/view?usp=sharing
> **Power BI Dashboard** | Emergency Room Operations Analysis — April 2023 to October 2024

---

## 📌 Problem Statement

The Hospital Emergency Room Dashboard provides an in-depth analysis of ER operations over a **19-month period (April 2023 – October 2024)**, covering **9,216 unique patient records**.

It helps hospital management monitor patient volumes, wait times, satisfaction scores, referrals, demographics, and admission patterns. Insights from this dashboard guide resource allocation, optimize staff scheduling, improve patient throughput, and enhance the overall patient experience.

---

## 📊 Dashboard Preview
<img width="1470" height="956" alt="Screenshot 2026-05-02 at 8 55 56 AM" src="https://github.com/user-attachments/assets/27127ba4-7475-43e1-9228-4bd5b18992b5" />


---

## 🔧 Steps Followed

1. **Requirement Gathering** — Collaborated with hospital administrators to identify key KPIs.
2. **Data Walkthrough** — Validated sources and understood field definitions.
3. **Data Connection** — Connected to hospital EMR & operational databases.
4. **Data Cleaning** — Removed nulls and corrected inconsistencies in patient records.
5. **Data Modeling** — Linked patient, department, and time dimension tables.
6. **Data Processing** — Prepared analysis-ready tables for reporting.
7. **DAX Calculations** — Built measures for patient counts, wait times, and satisfaction scores.
8. **Dashboard Layouting** — Designed layout for clarity and usability.
9. **Chart Development** — Built visuals for trends, breakdowns, and comparisons.
10. **Publishing** — Published to Power BI Service for team accessibility.

---

## 📋 Dashboards Created

The report contains four pages:

| Page | Purpose |
|------|---------|
| Monthly View | Track ER activity month-by-month |
| Consolidated View | Aggregated KPIs over any custom date range |
| Patient Details | Granular patient-level records |
| Key Takeaways | Summarized findings and actionable insights |

---

## 📈 Key Insights

### 1. Monthly View — February 2024 Example

| Metric | Value |
|--------|-------|
| No. of Patients | 431 |
| Avg Wait Time | 36.7 mins |
| Avg Satisfaction Score | 4.72 / 10 |
| Patients Referred | 179 |
| Admitted | 224 (51.97%) |
| Not Admitted | 207 (48.03%) |
| Seen within 30 mins | 283 (65.66%) |

### 2. Consolidated View — Apr 2023 to Aug 2024

| Metric | Value |
|--------|-------|
| No. of Patients | 7,982 |
| Avg Wait Time | 35.3 mins |
| Avg Satisfaction Score | 4.96 / 10 |
| Patients Referred | 3,298 |
| Admitted | 3,987 (49.95%) |
| Not Admitted | 3,995 (50.05%) |
| Seen within 30 mins | 5K (59.4%) |

### 3. Patient Details

Granular table with the following fields:
- Patient ID, Patient Name, Gender, Age
- Admission Date, Wait Time
- Department Referral, Admission Status

### 4. Key Takeaways (Full Period: Apr 2023 – Oct 2024)

**Overall KPIs:**
| Metric | Value |
|--------|-------|
| Total Unique Patients | 9,216 |
| Avg Wait Time | 35.3 mins |
| Avg Satisfaction Score | 4.99 / 10 |
| Total Admitted | 4,612 |
| Total Not Admitted | 4,604 |

**Top Departmental Referrals:**
| Department | Cases |
|---|---|
| None (No referral) | 5,400 |
| General Practice | 1,840 |
| Orthopedics | 995 |
| Physiotherapy | 276 |
| Cardiology | 248 |

**Peak Busy Periods:**
| Day | Patients |
|---|---|
| Monday | 1,377 |
| Saturday | 1,322 |
| Tuesday | 1,318 |

Busiest hours: **11 AM, 1 PM, 7 PM, and 11 PM**

**Patient Age Distribution:**
| Age Group | Patients |
|---|---|
| 30–39 years | 1,200 (largest group) |
| 20–29 years | 1,188 |
| 40–49 years | ~982 |

**Race Distribution:**
| Race | Count |
|---|---|
| White | 2,571 |
| African American | 1,951 |
| Multiracial | 1,557 |
| Asian | 1,060 |
| Declined to Identify | 1,030 |
| Pacific Islander | 464 |
| Native American | 444 |

---

## 🧮 DAX Measures

```dax
Total Patients = COUNT(Patients[Patient ID])

Average Wait Time = AVERAGE(Patients[Wait Time])

Average Satisfaction = AVERAGE(Patients[Satisfaction Score])

Referral Count = COUNT(Patients[Department Referral])

% Admitted = DIVIDE(
    COUNTROWS(FILTER(Patients, Patients[Admission Status] = "Admitted")),
    [Total Patients]
)

Seen Within 30 Min = COUNTROWS(
    FILTER(Patients, Patients[Wait Time] <= 30)
)
```

---

## 💡 Recommendations

- **Increase staffing on Mondays, Saturdays, and Tuesdays** — these are consistently the busiest days.
- **Schedule additional staff during 11 AM, 1 PM, 7 PM, and 11 PM** to handle peak hour surges.
- **Reduce wait times** — the current avg of 35.3 mins should be brought under 30 mins to meet best-practice targets.
- **Improve satisfaction scores** — 4.99/10 indicates significant room for improvement in patient experience.
- **Expand General Practice and Orthopedics capacity** — these are the highest-volume referral departments.
- **Focus on adult (30–49 years) demographic** — they form the largest patient segment.

---

## 🛠️ Tools & Technologies

- **Power BI Desktop** — Data modeling, DAX, and visualization
- **Power Query** — Data cleaning and transformation
- **Power BI Service** — Dashboard publishing and sharing
- **Data Source** — Hospital EMR & operational database (April 2023 – October 2024)

---

## 📁 Project Structure

```
hospital-er-dashboard/
├── Hospital_ER_Dashboard.pbix     # Power BI project file
├── data/
│   └── hospital_er_data.csv       # Source dataset
├── snapshots/
│   ├── monthly-view.png
│   ├── consolidated-view.png
│   ├── patient-details.png
│   └── key-takeaways.png
└── README.md                      # Project documentation
```

---

## 🚀 Getting Started

1. Clone or download this repository.
2. Open `Hospital_ER_Dashboard.pbix` in **Power BI Desktop**.
3. Update the data source path if needed via **Transform Data > Data Source Settings**.
4. Refresh the data and explore all four dashboard pages.

---

## 👤 Developed By

**Jyoti Khatri**

---

*Dashboard built for healthcare analytics and operational decision-making. All patient data is anonymized and used for analytical purposes only.*
