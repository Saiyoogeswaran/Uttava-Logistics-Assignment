# 📊 Excel Dashboard — Uttava Logistics Assignment

This project was created as part of a hiring assignment from **Ondru** for a Data Analyst role at **Uttava Logistics**. The task involved building an Excel dashboard using a sample dataset to demonstrate analytical thinking, visualization skills, and dashboard design.

---

## 🧠 Project Overview

# 📦 Excel Dashboard — Uttava Logistics Assignment (Ondru Private Limited)

This project showcases my analysis for a hiring assignment with **Ondru**, involving a dynamic dashboard for a sample Amazon dataset. The dashboard was built in Excel using Power Query, structured formulas, charts, and pivot tables.

---

## 🧹 Data Cleaning & Validation (Power Query)

Transformation logic applied in Power Query:

1. Changed datatype for **all columns**
2.  Applied `TRIM()` and `PROPER()` on `Traffic`, `Vehicle`, `Area`, and `Category`
3.  Used `LEN()` to verify uniformity of `Order_ID` length
4.  Created **conditional column** for:
  - Identifying if `Delivery_Time` is in minutes or hours
  - Filling `Agent_Rating` blanks using logic:
    - `<30 mins` → 4.5
    - `30–120 mins` → 3.5
    - `>120 mins` → 2
- Converted `0` latitude/longitude to blank for accuracy  
- Calculated **distance using Haversine formula**:  
  ```excel
  =IF(OR(ISBLANK(A1), ISBLANK(B1), ISBLANK(C1), ISBLANK(D1)), "", 
     6371 * ACOS(COS(RADIANS(90 - A1)) * COS(RADIANS(90 - B1)) + 
     SIN(RADIANS(90 - A1)) * SIN(RADIANS(90 - B1)) * COS(RADIANS(C1 - D1))))
5. **Order Time Formatting**  
   - Original column had NaN and general types  
   - Used formula:  
     `=IF(ISNUMBER([@[Order_Time]]), TEXT([@[Order_Time]],"hh:mm:ss"), "")`

6. **Weather & Traffic Columns**  
   - Replaced NaN values with `"No Data"`

7. **Delivery Time Interpretation**  
   - Used logic:  
     `Delivery_time <= 1440` → values are in minutes  
   - Confirmed delivery time format for further analysis

---

## 📊 Sheet-Level Analysis

### `Duplicate_Records`
- Checked for duplicates in Order_ID
- Applied conditional formatting with LEN()

### `Data_Analysis`
- Weather impact on delivery `(bar chart + COUNT())`
- Common transportation modes `(pie chart + COUNT() + SUM() + XLOOKUP() + MAX()/MIN())` 
- Customer concentration by region `(bar chart + SUM())`  
- Most/least ordered categories `(bar chart + COUNT() + XLOOKUP() + MAX()/MIN())`
- Traffic vs. average delivery time `(AVERAGE())`

### `Delivery_Analysis`
- Identified fastest and slowest deliveries using `VLOOKUP()`

### `Order_Analysis`
- Category-wise order count for Feb, Mar, Apr  
- Used `Data Validation` dropdown + `HLOOKUP()` + `MATCH()` for dynamic selection

### `Dynamic_Analysis`
1. **Monthwise Category Grouping**  
   - Fashion & Apparel, Sports & Games, Grocery & Foods, etc.

2. **Top 3 Categories per Month**  
   - Based on order count for Feb, Mar, Apr

3. **Vehicle & Traffic Analysis**  
   - Avg. distance, avg. time, and ranking by vehicle-traffic combinations

---

## 💬 Outcome & Reflection

The assignment was well-received by the hiring team, and I was told the dashboard genuinely impressed them. However, I didn’t perform well in the interview that followed. While the outcome wasn’t what I hoped for, the experience taught me a lot about preparation, presentation, and resilience.

---

## 🔒 File Protection

The Excel file is protected to preserve original formatting and formulas. Viewers can explore the dashboard but cannot modify its contents.

---

## 📚 Credits

- Dataset provided as part of the assignment
- Dashboard design inspired by best practices learned through self-study

---

## 🔗 Connect with Me

This project is part of my ongoing data journey. Feel free to explore, share feedback, or connect on [LinkedIn](https://www.linkedin.com/in/contactsaiyoogeswaran/).

> Every assignment is a stepping stone. This one taught me how to turn feedback into fuel.
