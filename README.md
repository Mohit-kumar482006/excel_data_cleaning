# 🧹 Messy Orders Dataset — Data Cleaning Project

A data cleaning project built around a deliberately messy customer orders dataset. The workbook contains a raw sheet full of real-world data quality issues and a cleaned version that resolves them — making it a great hands-on exercise for learning data cleaning techniques in Excel or Python (pandas).

---

## Workbook Structure

| Sheet | Description |
|---|---|
| `Customer Orders` | Raw, uncleaned data with multiple quality issues |
| `clean_customer_orders` | Cleaned version with fixes and an added validation column |

---

## Dataset Overview

| Column | Description |
|---|---|
| `Order ID` | Unique order identifier (e.g. ORD-001) |
| `Customer Name` | Name of the customer |
| `Email` | Customer email address |
| `Phone` | Customer phone number |
| `Product` | Product ordered |
| `Quantity` | Units ordered |
| `Unit Price` | Price per unit (₹) |
| `Total` | Total order value |
| `Order Date` | Date of order |
| `Status` | Order status (Delivered, Shipped, Pending, Cancelled) |
| `Region` | North, South, East, West |

**Rows:** 25 | **Products:** 10 | **Salespersons/Regions:** 4

---

## Data Quality Issues (Raw Sheet)

| Issue | Example |
|---|---|
| Inconsistent date formats | `2024-01-15`, `15/01/2024`, `Jan 16, 2024`, `17-01-2024` |
| Inconsistent casing in Status | `Delivered`, `delivered`, `DELIVERED`, `Deliverd` |
| Inconsistent casing in Region | `North`, `NORTH`, `south` |
| Inconsistent casing in Names | `john smith`, `PRIYA SHARMA`, `Rahul Verma` |
| Invalid email addresses | `rahulverma@@gmail.com`, `rohit.kumar@gmail` |
| Missing values | Null phone numbers, missing customer name |
| Negative quantity | `-1` for a return/error entry |
| Wrong Total calculation | `Headphones` row: Qty 1 × ₹3500 = ₹35,000 (should be ₹3,500) |
| Mixed Total format | Some values as `55,000` (text) vs `55000` (number) |
| Zero total | One entry with ₹0 total |

---

## What Was Cleaned (`clean_customer_orders` sheet)

| Fix | How |
|---|---|
| Standardized dates | All converted to `YYYY-MM-DD` format |
| Standardized Status & Region | Proper case applied throughout |
| Standardized Names | Title case applied (e.g. `john smith` → `John Smith`) |
| Email validation | Added `Email Valid/Invalid` column flagging bad emails |
| Negative quantity flagged | Marked as `Invalid` in Quantity column |

---

## Concepts Covered

| Concept | Where |
|---|---|
| Handling missing values | Null phone and name fields |
| Fixing inconsistent casing | Status, Region, Customer Name |
| Date format standardization | Multiple date formats in one column |
| Data type issues | Total column mixing text and numbers |
| Email validation | Regex-style pattern check |
| Flagging invalid entries | Negative quantity, wrong totals |
| Adding derived/validation columns | `Email Valid/Invalid` column in cleaned sheet |

---

## How to Use

1. Open `messy_orders_dataset.xlsx` in Excel or load it with pandas
2. Study the `Customer Orders` sheet to spot the issues
3. Compare with `clean_customer_orders` to see how each issue was resolved
4. Use it as practice for data cleaning in **Excel**, **Python (pandas)**, or **SQL**

```python
import pandas as pd

raw = pd.read_excel('messy_orders_dataset.xlsx', sheet_name='Customer Orders')
clean = pd.read_excel('messy_orders_dataset.xlsx', sheet_name='clean_customer_orders')
```
