# 📊 Salon & Spa Dashboard -- Databricks

## 📂 Dataset

The dataset contains salon and spa customer details with the following
columns:\
- **Customer ID, Name, Gender, Age, Contact, Email**\
- **Membership Status** (Yes/No, Gold/Silver/Platinum)\
- **Popular Service, Service Type, Category**\
- **Peak Time** (Morning, Afternoon, Evening, Weekend)\
- **Payment Mode** (Cash, Card, UPI, Wallet)\
- **Customer Feedback/Rating** (1--5 stars)

------------------------------------------------------------------------

## 🚀 Steps to Run in Databricks

### 1. Upload Dataset

1.  Go to **Data → Add Data → Upload File**.\
2.  Upload `salon_spa_dataset.csv`.\
3.  Save as a table: `default.salon_spa_dataset`.

------------------------------------------------------------------------

### 2. Verify Data

``` sql
SHOW TABLES IN default;
SELECT * FROM salon_spa_dataset LIMIT 10;
```

------------------------------------------------------------------------

### 3. Queries & Use Cases

#### 3.1 Most Popular Services

``` sql
SELECT ServiceType, COUNT(*) AS Total_Bookings
FROM salon_spa_dataset
GROUP BY ServiceType
ORDER BY Total_Bookings DESC;
```

📊 Bar Chart

#### 3.2 Peak Time Analysis

``` sql
SELECT PeakTime, COUNT(*) AS Total_Visits
FROM salon_spa_dataset
GROUP BY PeakTime
ORDER BY Total_Visits DESC;
```

📊 Pie Chart

#### 3.3 Membership Insights

``` sql
SELECT MembershipStatus, COUNT(*) AS Members
FROM salon_spa_dataset
GROUP BY MembershipStatus
ORDER BY Members DESC;
```

📊 Donut Chart

#### 3.4 Average Rating by Service

``` sql
SELECT ServiceType, AVG(`Customer Feedback/Rating`) AS Avg_Rating
FROM salon_spa_dataset
GROUP BY ServiceType
ORDER BY Avg_Rating DESC;
```

📊 Bar Chart

#### 3.5 Gender vs Service Preference

``` sql
SELECT Gender, ServiceType, COUNT(*) AS Total
FROM salon_spa_dataset
GROUP BY Gender, ServiceType
ORDER BY Total DESC;
```

📊 Grouped Bar Chart

------------------------------------------------------------------------

### 4. Create Dashboard

1.  Run each query in **Databricks SQL Editor**.\
2.  Add a **Visualization** for each query.\
3.  Save and **Add to Dashboard**.\
4.  Arrange tiles to build *Salon & Spa Insights Dashboard*.

------------------------------------------------------------------------

## ✅ Dashboard Includes

-   **Popular Services**\
-   **Peak Time Analysis**\
-   **Membership Distribution**\
-   **Average Ratings by Service**\
-   **Gender-wise Preferences**
