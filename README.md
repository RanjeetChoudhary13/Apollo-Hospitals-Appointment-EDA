# Apollo Hospitals - Appointment No-Show & Patient Engagement Analysis

### Analytics by Ranjeet Anada

A comprehensive **Exploratory Data Analysis (EDA)** project using Python to analyse appointment behaviour, patient no-shows, engagement patterns, financial performance, doctor utilisation, and service quality across Apollo Hospitals.

---

## Project Overview

Apollo Hospitals operates across multiple cities in India through different consultation modes such as:

- In-Clinic Consultations
- Video Consultations
- Home Visits

Patients book appointments through multiple channels including:

- Apollo App
- Website
- Call Centre
- Walk-In
- Partner App

A key operational challenge is **appointment no-shows**, which can negatively affect doctor utilisation, hospital revenue, operational efficiency, and continuity of patient care.

This project analyses **75,000 appointment records from 2022 to 2024** to identify patterns, risk factors, and actionable business insights.

---

## Business Objectives

The main objectives of this project are to:

- Analyse monthly and quarterly appointment trends
- Understand appointment outcome distribution
- Analyse booking channel volume and mix
- Identify specialties and cities with high no-show rates
- Measure the effect of booking lead time on no-show behaviour
- Compare no-show risk across time of day and weekends
- Analyse appointment type and booking channel risk
- Measure reminder effectiveness
- Evaluate the impact of previous no-show history
- Compare member vs non-member behaviour
- Compare first-time vs repeat patient behaviour
- Analyse demographic patterns
- Measure financial performance and revenue exposure
- Analyse doctor utilisation and patient waiting time
- Study consultation duration and patient satisfaction
- Analyse the relationship between doctor experience and consultation fee

---

## Dataset

The project uses two main datasets.

### 1. Appointment Fact Dataset

**File:** `apollo_appointments_fact.csv`

- 75,000 rows
- 52 columns
- One row represents one appointment
- Covers appointment activity from 2022 to 2024

The dataset contains information related to:

- Appointment date and time
- Booking channel
- Appointment type
- Specialty
- City
- Patient demographics
- Membership
- Reminder communication
- Previous visits and no-shows
- Appointment status
- Revenue
- Insurance
- Payment method
- Wait time
- Consultation duration
- Patient satisfaction
- Doctor utilisation

### 2. Doctor Dimension Dataset

**File:** `apollo_doctors_dim.csv`

- 320 doctors
- 15 columns
- One row represents one doctor

The dataset contains doctor-level information such as:

- Doctor name
- Specialty
- Experience
- Qualification
- City
- Hospital
- Consultation fee
- Rating
- Reviews
- Insurance acceptance
- Teleconsult availability

The two datasets are linked using:

```python
doctor_id
```

---

## Tools & Technologies

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Jupyter Notebook**
- **VS Code**
- **Git & GitHub**

---

## Project Workflow

The project follows a structured analytical workflow:

1. Data Loading
2. Dataset Inspection
3. Data Quality Validation
4. Business Rule Validation
5. Exploratory Data Analysis
6. Appointment Trend Analysis
7. No-Show Analysis
8. Patient Engagement Analysis
9. Demographic Analysis
10. Financial Analysis
11. Doctor Utilisation Analysis
12. Service Quality Analysis
13. Data Visualization
14. Business Insights
15. Business Recommendations

---

## Important Business Rules

### No-Show Rate

Scheduled appointments are excluded from the no-show-rate denominator.

```text
No-Show Rate =
No-Show /
(Completed + No-Show + Cancelled)
```

### Quality Metrics

The following metrics are analysed only for **Completed appointments**:

- Wait Time
- Consultation Duration
- Patient Satisfaction
- Doctor Utilisation

### Revenue Analysis

Revenue-related fields are analysed only for **Completed appointments**.

For no-show financial analysis, the listed consultation fee is used to estimate potential consultation-fee exposure associated with missed appointments.

### Not Applicable Values

`None` in fields such as:

- Chronic Condition
- Membership Type
- Insurance Provider
- Cancellation Reason

is treated as **Not Applicable**, rather than missing data.

### Doctor-Level Analysis

Doctor experience vs consultation fee is analysed using the **Doctor Dimension dataset**, where each doctor appears once, to avoid appointment-level duplication.

---

# Exploratory Data Analysis

## 1. Appointment & Business Overview

The analysis includes:

- Monthly appointment volume
- Quarterly appointment volume
- Appointment outcome distribution
- Booking channel volume and mix

### Key Observation

The **Apollo App** is the dominant booking channel and contributes approximately **45% of total appointment volume**.

---

## 2. No-Show Analysis

No-show behaviour is analysed across:

- Specialty
- City
- Booking Lead Time
- Time of Day
- Weekday vs Weekend
- Appointment Type
- Booking Channel

### Key Findings

- Overall analytical no-show rate is approximately **15.94%**
- Psychiatry shows one of the highest specialty-level no-show rates
- Longer booking lead times are associated with higher no-show risk
- Appointments booked **22-30 days in advance** show approximately **22% no-show rate**
- Evening appointments show higher no-show risk than morning appointments
- Weekend appointments show higher no-show rates than weekdays
- **Home Visits** show the highest no-show rate among appointment types
- **Walk-In appointments** show the highest no-show rate among booking channels

---

## 3. Reminder & Patient Engagement Analysis

The analysis evaluates:

- Reminder effectiveness
- Previous no-show history
- Apollo membership
- First-time vs repeat patients

### Key Findings

Patients receiving multiple reminders show significantly better attendance behaviour.

The strongest reminder combination:

```text
SMS + WhatsApp + Call
```

shows an observed no-show rate of approximately **11.4%**, while patients receiving **No Reminder** show approximately **30.2%**.

Previous no-show history also shows a strong relationship with future no-show behaviour.

Patients with multiple previous no-shows have substantially higher current no-show risk.

Apollo members also show better appointment adherence than non-members.

---

## 4. Patient & Demographic Analysis

No-show behaviour is analysed by:

- Age Group
- Gender
- Chronic Condition
- Visit Reason

The project also analyses patient age distribution within:

- Paediatrics
- Gynaecology
- Psychiatry

Visit reason analysis includes both:

- Appointment Volume
- No-Show Rate

This helps identify the difference between **high-volume visit categories** and **high-risk visit categories**.

---

## 5. Financial Performance

Financial analysis includes:

- Estimated financial exposure from no-shows
- Average realized revenue by specialty
- Average realized revenue by appointment type
- Total realized revenue by city
- Payment mode mix
- Insurance coverage vs patient out-of-pocket payment

### Key Findings

- Bengaluru and Delhi are among the strongest cities by total realized revenue
- Psychiatry records one of the highest average realized revenue values by specialty
- **Home Visits** generate the highest average realized revenue among appointment types
- Insurance is the largest individual payment-mode category
- Insurance coverage substantially reduces the average amount paid directly by patients

---

## 6. Doctor Utilisation & Service Quality

The analysis evaluates:

- Doctor utilisation by specialty
- Wait time by specialty and time of day
- Consultation duration vs patient satisfaction
- Doctor experience vs standard consultation fee

### Key Findings

Doctor utilisation remains relatively consistent across specialties, generally in the mid-to-high **70% range**.

Average patient wait time varies slightly across specialty and time-of-day combinations.

The relationship between consultation duration and patient satisfaction is almost negligible:

```text
Correlation ≈ -0.004
```

Doctor experience shows a weak positive relationship with standard consultation fee:

```text
Correlation ≈ 0.278
```

This suggests that experience contributes to consultation pricing, but other factors also influence doctor fees.

---

# Key Business Insights

### 1. Long Booking Lead Times Increase Risk

Appointments scheduled far in advance show a higher probability of no-show behaviour.

### 2. Reminder Communication Is Highly Effective

Multi-channel reminders are associated with significantly better appointment attendance.

### 3. Previous No-Shows Are a Strong Risk Indicator

Patients with previous missed appointments are much more likely to miss future appointments.

### 4. First-Time Patients Need Stronger Engagement

New patients require additional communication and appointment guidance.

### 5. Some Appointment Types Carry Higher Risk

Home Visits show considerably higher no-show risk than In-Clinic consultations.

### 6. Weekend and Evening Appointments Need Attention

Both segments show higher observed no-show behaviour.

### 7. Digital Booking Is Important

The Apollo App contributes the largest share of appointment volume.

### 8. No-Shows Have Financial Impact

Reducing missed appointments can improve both doctor utilisation and revenue realization.

---

# Business Recommendations

### Strengthen Multi-Channel Reminder Systems

Use combinations such as:

```text
SMS + WhatsApp + Call
```

for high-risk appointments.

### Introduce Risk-Based Appointment Confirmation

Additional confirmation should be prioritised for:

- Patients with previous no-shows
- Long-lead bookings
- Weekend appointments
- Evening appointments
- Home Visits
- First-time patients

### Improve First-Time Patient Communication

Provide clearer:

- Appointment instructions
- Location information
- Reminder communication
- Rescheduling options

### Monitor High-Risk Specialties and Cities

Create recurring operational KPIs for:

- No-show rate
- Appointment volume
- Doctor utilisation
- Revenue exposure

### Strengthen Digital Patient Engagement

Continue improving Apollo App adoption and engagement because it represents the largest booking channel.

### Monitor Financial Impact of No-Shows

Track estimated consultation-fee exposure from missed appointments as a regular business KPI.

### Continue Service Quality Monitoring

Regularly track:

- Patient Wait Time
- Doctor Utilisation
- Patient Satisfaction
- Consultation Duration

---

# Project Visualizations

The project contains **30 professional visualizations** covering:

- Monthly Appointment Trends
- Quarterly Appointment Trends
- Appointment Outcome Mix
- Booking Channel Mix
- No-Show Rate by Specialty
- No-Show Rate by City
- Booking Lead-Time Risk
- Time-of-Day Risk
- Weekend vs Weekday
- Appointment Type Risk
- Booking Channel Risk
- Reminder Effectiveness
- Previous No-Show History
- Apollo Membership
- Repeat vs First-Time Patients
- Age Group
- Gender
- Chronic Conditions
- Visit Reason Volume
- Visit Reason No-Show Risk
- Specialty-Level Age Distribution
- Revenue by Specialty
- Revenue by Appointment Type
- Revenue by City
- Payment Mode Mix
- Insurance Analysis
- Doctor Utilisation
- Wait-Time Heatmap
- Consultation Duration vs Satisfaction
- Doctor Experience vs Consultation Fee

### Full Visualization Report

[View Apollo Hospitals - All Charts PDF](./Apollo_Hospitals_All_Charts.pdf)

---

# Project Files

| File | Description |
|---|---|
| [Apollo_Hospitals_EDA.ipynb](./Apollo_Hospitals_EDA.ipynb) | Complete Python EDA notebook with code, outputs and visualizations |
| [Apollo_Hospitals_All_Charts.pdf](./Apollo_Hospitals_All_Charts.pdf) | Complete 30-chart visualization report |
| `data/apollo_appointments_fact.csv` | Main appointment-level dataset |
| `data/apollo_doctors_dim.csv` | Doctor dimension dataset |
| `data/Data Dictionary.docx` | Dataset field definitions and business rules |

---

# Repository Structure

```text
Apollo-Hospitals-Appointment-EDA/
│
├── data/
│   ├── apollo_appointments_fact.csv
│   ├── apollo_doctors_dim.csv
│   └── Data Dictionary.docx
│
├── Apollo_Hospitals_All_Charts.pdf
├── Apollo_Hospitals_EDA.ipynb
└── README.md
```

---

# How to Run the Project

## 1. Clone the Repository

```bash
git clone <your-repository-url>
```

## 2. Open the Project Folder

Open the repository using:

- VS Code
- Jupyter Notebook
- JupyterLab

## 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

## 4. Open the Notebook

```text
Apollo_Hospitals_EDA.ipynb
```

## 5. Run All Cells

Run the notebook from top to bottom to reproduce the complete analysis and visualizations.

---

# Project Deliverables

- Complete Python EDA Notebook
- 75,000 Appointment Analysis
- Doctor Dimension Analysis
- 30 Professional Visualizations
- Full Charts PDF Report
- Business Insights
- Business Recommendations
- Data Dictionary
- Portfolio-Ready GitHub Documentation

---

## Skills Demonstrated

`Python` `Pandas` `NumPy` `Matplotlib` `Seaborn` `EDA` `Data Cleaning` `Data Visualization` `Business Analysis` `Healthcare Analytics`

---

# Author

## Analytics by Ranjeet Anada

**Data Analyst**

This project was developed as a Data Analytics portfolio project to demonstrate practical skills in:

- Python Exploratory Data Analysis
- Business Problem Solving
- Healthcare Data Analysis
- Data Visualization
- Analytical Thinking
- Insight Generation
- Business Recommendations

---

⭐ If you found this project useful, feel free to explore the notebook and visualization report.
