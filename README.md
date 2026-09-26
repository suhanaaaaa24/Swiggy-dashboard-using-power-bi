# # Swiggy Order Analytics Dashboard Using Power BI

## Project Overview

This project presents an interactive Swiggy-style Order Analytics Dashboard developed using Microsoft Power BI.

The dashboard analyzes order revenue, order volume, customer behavior, restaurant performance, cuisine, city, payment methods, delivery performance, discounts, and cancellations.

The project uses a structured data model with Orders, Customers, and Restaurants tables and combines Power Query, calculated columns, DAX measures, and interactive visualizations to create a decision-ready dashboard.

---

## Project Objectives

The main objectives of this project are:

- Analyze overall order revenue and order volume
- Track revenue trends over time
- Identify top-performing restaurants
- Compare revenue and order volume across cities
- Analyze payment method preferences
- Compare order status across different cuisines
- Analyze restaurant ratings and average order value
- Monitor delivery performance
- Understand cancellation patterns
- Analyze customer ordering behavior
- Understand the impact of discounts on orders and revenue

---

## Dataset Overview

The project uses three connected tables:

### 1. Orders

**Fact Table**

Contains approximately 8,000 order records.

Main columns include:

- OrderID
- CustomerID
- RestaurantID
- OrderDate
- OrderTime
- DeliveryTimeMin
- ItemsCount
- OrderValue
- DiscountAmount
- DeliveryFee
- PaymentMethod
- OrderStatus

### 2. Customers

**Dimension Table**

Contains approximately 600 customer records.

Main columns include:

- CustomerID
- CustomerName
- Gender
- Age
- City
- SignupDate

### 3. Restaurants

**Dimension Table**

Contains approximately 250 restaurant records.

Main columns include:

- RestaurantID
- RestaurantName
- City
- Cuisine
- Rating
- CostForTwo
- FoodType

The Orders table is connected to the Customers and Restaurants tables through CustomerID and RestaurantID relationships.

---

## Tools & Technologies Used

- Microsoft Power BI
- Power Query
- DAX
- CSV Data
- Data Modeling
- Data Visualization

---

## Data Cleaning

Power Query was used to prepare the data before building the dashboard.

The cleaning process included:

- Removing duplicate OrderID records
- Setting appropriate data types
- Cleaning and trimming text fields
- Standardizing city names
- Handling missing DeliveryTimeMin and Rating values
- Filtering invalid orders where OrderValue was less than or equal to zero
- Combining OrderDate and OrderTime into a DateTime field
- Validating CustomerID and RestaurantID relationships

---

## Data Modeling

A star-schema approach was used for the Power BI data model.

The model consists of:

- Orders — Fact Table
- Customers — Dimension Table
- Restaurants — Dimension Table

Relationships:

```text
Customers
    │
    │ CustomerID
    ▼
Orders
    ▲
    │ RestaurantID
    │
Restaurants
