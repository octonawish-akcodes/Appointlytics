# Appointlytics

## Project Overview

This project analyzes a dataset of 100k medical appointments in Brazil to uncover factors influencing whether or not patients show up for their appointments. The analysis explores correlations between demographic and health-related factors with patient behavior, aiming to provide actionable insights into improving appointment attendance rates.

---

## Dataset Description

The dataset contains detailed information about medical appointments, including patient demographics, health conditions, and whether they showed up for the appointment.  

- **Source**: [Kaggle](https://www.kaggle.com/datasets/joniarroba/noshowappointments)  
- **File**: `noshowappointments-kagglev2-may-2016.csv`  

---

## Columns Description

1. `PatientId`: Unique identifier for each patient.  
2. `AppointmentID`: Unique identifier for each appointment.  
3. `Gender`: Gender of the patient (Male/Female).  
4. `ScheduledDay`: Date the appointment was scheduled.  
5. `AppointmentDay`: Actual date of the appointment.  
6. `Age`: Age of the patient.  
7. `Neighbourhood`: Location of the clinic.  
8. `Scholarship`: Indicates whether the patient is enrolled in the Bolsa Família program.  
9. `Hipertension`: Indicates if the patient has hypertension.  
10. `Diabetes`: Indicates if the patient has diabetes.  
11. `Alcoholism`: Indicates if the patient has a history of alcoholism.  
12. `Handcap`: Indicates if the patient has a disability.  
13. `SMS_received`: Indicates if the patient received a reminder SMS.  
14. `No-show`: Indicates if the patient showed up for the appointment (True/False).  

---

## EDA Questions

1. How often do men attend appointments compared to women? Which gender is more likely to show up?  
2. Does receiving an SMS reminder affect attendance rates? Is it correlated with the number of days before the appointment?  
3. Does having a scholarship affect attendance? Which age groups are impacted?  
4. Do health conditions like hypertension, diabetes, or alcoholism influence attendance rates? Is this affected by gender?  

---

## Workflow

Below is a flowchart representing the project's workflow:

```plaintext
+------------------+       +------------------+       +-------------------+
| Load Dataset     | --->  | Data Wrangling   | --->  | Data Cleaning      |
+------------------+       +------------------+       +-------------------+
                                                           |
                                                           v
           +-------------------+       +-------------------------+
           | Exploratory Data  | --->  | Data Visualization       |
           | Analysis (EDA)    |       +-------------------------+
           +-------------------+
                                                           |
                                                           v
           +-----------------------------------------------+
           | Conclusions and Insights                     |
           +-----------------------------------------------+
```

---

## Data Wrangling

- **File**: `noshowappointments-kagglev2-may-2016.csv`  
- Removed unnecessary columns like `PatientId` and `AppointmentID`.  
- Converted date fields (`ScheduledDay`, `AppointmentDay`) to datetime format.  
- Added a new column for the number of days between scheduling and the appointment date.  
- Categorized and transformed certain columns for efficient analysis.

---

## Data Cleaning

### Summary of Cleaning Process
- **Initial Data**: 110,527 rows and 14 columns.  
- No NaN or duplicate values found.  
- Addressed inconsistencies in the `Handcap` and `Age` columns.  
- Transformed `Gender`, `Scholarship`, `Hipertension`, `Diabetes`, `Alcoholism`, and `SMS_received` into categorical or boolean types.  
- **Cleaned Data**: 110,521 rows and 11 columns.  

---

## Data Visualization

Using **Matplotlib** and **Seaborn**, we created visualizations to uncover relationships between attributes, such as:  
- Gender-based attendance rates.  
- The impact of SMS reminders.  
- Attendance trends based on scholarship status and chronic diseases.  

---

## Conclusion

### Insights:
- **Gender**: Women are more likely to show up for appointments, but this is influenced by their higher representation in the dataset.  
- **SMS Reminders**: Receiving an SMS has a marginal impact on attendance; however, shorter wait times correlate positively with attendance.  
- **Scholarships**: Minimal impact on attendance rates, with diverse age groups benefiting from the program.  
- **Chronic Diseases**: Patients with chronic conditions are less likely to attend their appointments, especially younger patients.  

---

## Built With

- **JupyterLab**  
- **Python 3**  
- **Pandas**  
- **Numpy**  
- **Matplotlib**  
- **Seaborn**  

---
