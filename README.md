## 🚗 Uber Ride Analytics Dashboard (2024)

## Dashboard Preview
<img src="Images/dashboard3.jpg" width="750"/>
<img src="Images/dashboard3.1.jpg" width="750"/>

An interactive **Power BI analytics dashboard** designed to analyze Uber ride data and uncover insights related to **peak demand periods, pricing behavior, ride cancellations, payment preferences, and operational efficiency**.  
This project demonstrates strong capabilities in 
** 
   - Power Query (data cleaning, transformation, custom columns)
   - DAX modeling
   - Analytical Storytelling


---

## 📌 Project Overview

This dashboard analyzes Uber ride data from **NCR, India (2024)** to support **data-driven decision-making** for ride-hailing operations.  
It focuses on understanding customer behavior, driver performance, and pricing dynamics using interactive visual analytics.

---

## 📊 Key Objectives

- Identify **peak booking hours** and demand patterns  
- Analyze **pricing trends** by time of day and distance  
- Understand **ride cancellations** and their underlying causes  
- Examine **customer payment preferences**  
- Provide **actionable business recommendations**

---

## 🗂 Dataset Information

- **Source:** Kaggle – Uber Ride Analytics Dataset 2024  
- **Dataset Size:** ~25 MB  
- **Records:** ~148,000 rows  
- **Region:** NCR, India  
- **Scope:**  
  - Booking time & status  
  - Ride distance  
  - Vehicle type  
  - Payment methods  
  - Customer ratings  
  - Cancellation reasons  

🔗 Dataset Link:  
https://www.kaggle.com/datasets/yashdevladdha/uber-ride-analytics-dashboard

---

## ⚙️ Tools & Technologies

- **Power BI**
- **Power Query**
- **DAX (Data Analysis Expressions)**
- **Data Visualization & Analytics**
- **GitHub (Version Control)**

---

## 🧹 Data Preparation & Cleaning

Data preprocessing was performed using **Power Query** and **DAX**, addressing key quality challenges:

- Over **50% null values** in cancellation-related fields  
- Inconsistent booking status labels  

### Data Handling Approach

- Created **binary indicator columns** to normalize mixed-status fields:
  - Cancelled by Driver  
  - Cancelled by Customer  
  - Incomplete Rides  
  - Cancellation Reasons  
- Applied **visual-level and page-level filters** to prevent unnecessary row loss  
- Preserved nearly **90% of the original dataset**

---

## 🧮 DAX Calculations

### Time of Day Classification

```DAX
Time of Day = 
VAR Hour = HOUR('Uber Ride Analytics Dataset 2024'[Time])
RETURN
SWITCH(
    TRUE(),
    Hour >= 5  && Hour < 12, "Morning",
    Hour >= 12 && Hour < 17, "Afternoon",
    Hour >= 17 && Hour < 21, "Evening",
    Hour >= 21 || Hour < 5,  "Night"
)
```
---
Distance Range Bucketing
```Dax
Distance Range = 
SWITCH(
    TRUE(),
    'Uber Ride Analytics Dataset 2024'[Ride Distance] < 10, "1 - 10",
    'Uber Ride Analytics Dataset 2024'[Ride Distance] < 20, "11 - 20",
    'Uber Ride Analytics Dataset 2024'[Ride Distance] < 30, "21 - 30",
    'Uber Ride Analytics Dataset 2024'[Ride Distance] < 40, "31 - 40",
    'Uber Ride Analytics Dataset 2024'[Ride Distance] < 50, "41 - 50",
    "null"
)
```
---
## Key Insights

- Peak Demand:
Morning and evening hours show the highest number of completed bookings, corresponding to peak commuting times.

- Pricing Behavior:
Night-time rides have the highest average prices, indicating surge pricing effects. Daytime prices show moderate variation.

- Distance vs Pricing:
Average booking prices show minimal variation across distance ranges, suggesting pricing is driven more by demand and timing than distance.

- Payment Preferences:
UPI is the most commonly used payment method, significantly outperforming cash and card options.

- Ride Cancellations:
Customer cancellations increase when driver pickup time is high, making wait time a critical factor for ride completion.

---
## 💡 Recommendations

- Optimize Driver Allocation:
Increase driver availability during morning and evening peak hours using dynamic scheduling and incentives.

- Reduce Pickup Delays:
Improve driver–passenger matching by prioritizing proximity and enabling real-time reassignment.

- Refine Night-Time Pricing:
Enhance pricing transparency and introduce off-peak discounts or loyalty programs.

- Enhance Digital Payments:
Promote UPI-exclusive offers and ensure high transaction reliability to maintain user trust.

---




