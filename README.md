# Apollo Hospitals - Appointment No-Show and Patient Engagement Analysis

## Project Overview

This project performs Exploratory Data Analysis (EDA) on Apollo Hospitals appointment data to identify patterns related to appointment volume, no-shows, patient engagement, financial performance, and service quality.

The analysis covers 75,000 appointments recorded across 15 cities in India from 2022 to 2024.

## Business Objective

The objective of this project is to identify actionable insights that can help Apollo Hospitals:

- Reduce appointment no-shows
- Improve patient engagement and appointment adherence
- Understand booking channel and appointment type behaviour
- Identify high-risk no-show segments
- Analyse revenue impact of no-shows
- Understand financial and payment patterns
- Monitor doctor utilisation and service quality

## Dataset

The project uses two datasets:

### 1. Appointment Fact Dataset

**File:** `apollo_appointments_fact.csv`

- 75,000 rows
- 52 columns
- One row represents one appointment

### 2. Doctor Dimension Dataset

**File:** `apollo_doctors_dim.csv`

- 320 rows
- 15 columns
- One row represents one doctor

The two datasets are joined using `doctor_id` when doctor-level attributes are required.

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Analysis Performed

### Appointment & Business Overview

- Monthly appointment trends from 2022–2024
- Quarterly appointment trends
- Appointment outcome distribution
- Booking channel volume and mix

### No-Show Analysis

- No-show rate by specialty
- No-show rate by city
- Booking lead time analysis
- Weekend vs weekday analysis
- Time-of-day analysis
- Appointment type analysis
- Booking channel no-show analysis

### Reminder & Patient Engagement

- Reminder type effectiveness
- Prior no-show history
- Apollo member vs non-member attendance
- First-time vs repeat patient attendance

### Patient & Demographic Analysis

- Age group vs no-show rate
- Gender vs no-show rate
- Chronic condition analysis
- Visit reason frequency
- Visit reason vs no-show rate
- Patient age distribution across Paediatrics, Gynaecology and Psychiatry

### Financial Analysis

- Estimated revenue exposure from no-shows
- Average realized revenue by specialty
- Average realized revenue by appointment type
- Revenue by city
- Payment mode mix
- Insurance coverage vs patient out-of-pocket amount

### Doctor & Service Quality

- Doctor utilisation by specialty
- Wait time by specialty and time of day
- Consultation duration vs patient satisfaction
- Doctor experience vs actual fee charged

## Key Findings

- Overall no-show rate was **15.94%**, excluding Scheduled appointments from the denominator.
- Walk-In appointments recorded the highest no-show rate among booking channels.
- Psychiatry recorded the highest specialty-level no-show rate.
- Lucknow recorded the highest city-level no-show rate.
- Weekend and evening appointments showed higher observed no-show rates.
- Home Visits recorded the highest no-show rate among appointment types.
- Appointments without reminders showed the highest observed no-show rate.
- Patients with previous no-shows generally showed higher current no-show rates.
- Repeat patients showed substantially lower no-show rates than first-time patients.
- The estimated consultation-fee revenue exposure associated with no-shows was approximately **₹1.97 crore**.
- Bengaluru recorded the highest total realized revenue, closely followed by Delhi.
- Doctor utilisation was relatively consistent across specialties.
- Consultation duration showed almost no linear relationship with patient satisfaction.
- Doctor experience showed a weak positive relationship with actual fee charged.

## Business Recommendations

1. Strengthen reminder and confirmation processes for high-risk appointment segments.
2. Pay special attention to weekend and evening appointments.
3. Introduce additional confirmation steps for Home Visits and Video Consults.
4. Provide stronger appointment guidance and confirmation for first-time patients.
5. Monitor patients with previous no-show history more closely.
6. Focus no-show reduction initiatives on high-risk specialties and cities.
7. Monitor the financial impact of no-shows as a regular business KPI.
8. Strengthen payment-status tracking for pending payments.
9. Continue monitoring wait time, doctor utilisation and patient satisfaction.

## Project Structure

```text
Apollo-Hospitals-Appointment-EDA/
│
├── Apollo_Hospitals_EDA.ipynb
├── README.md
│
├── data/
│   ├── apollo_appointments_fact.csv
│   └── apollo_doctors_dim.csv
│
└── images/
