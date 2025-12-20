 🛒 E-commerce Price Drop Alert (n8n + Google Sheets)

This project detects product price drops and sends email alerts automatically.

## 🚀 Tech Stack
- n8n (workflow automation)
- Google Sheets (price history storage)
- JavaScript (price comparison logic)
- SQL (price drop detection logic)

## 🔄 Workflow Overview
1. Fetch product data from DummyJSON API
2. Store product prices in Google Sheets
3. Compare latest price with previous price
4. Trigger email alert only if price drops

## 🧠 Key Logic
- Each product has multiple price records
- Latest price is compared with the previous one
- Email is sent **only when price drops**
- No action is taken if price stays same or increases

## 📊 Data Structure (Google Sheets)
| id | title | category | price | rating | stock | fetched_at |
|----|-------|----------|-------|--------|-------|------------|

## ✉️ Email Alert
Alert is triggered only when price drops

## Issues Faced & Fixes

### 1. Multiple rows added unintentionally
Cause: Append row placed before IF node.
Fix: Append only after filtering logic.

### 2. Price treated as string
Cause: Google Sheets stores values as text.
Fix: Converted price to Number in JS.

### 3. Multiple items passing IF condition
Cause: IF checked absolute price (<10) instead of price drop.
Fix: Compared previous_price vs current_price.

### 4. Wrong previous_price selected
Cause: Rows not sorted by fetched_at.
Fix: Sorted rows in descending order before comparison.

### 5. False branch confusion
Fix: Left false branch empty intentionally.

# 🛒 E-commerce Price Drop Alert System

An automation project that tracks e-commerce product prices, detects real price drops, and sends email alerts automatically.

---

## 📌 Overview
This project monitors product prices over time and notifies users **only when a price drop occurs**.

It demonstrates:
- Automation using n8n
- Historical data tracking
- Conditional logic
- SQL-style analytical thinking

![Overview](images/overview.png)

---

## 🛠 Tech Stack
- n8n (Workflow Automation)
- Google Sheets (Price History Storage)
- JavaScript (Price Comparison Logic)
- SQL (Analytical Logic)
- Email (Alert Notifications)

---

## 🔄 n8n Workflow
The workflow fetches product data, stores price history, compares prices, and triggers alerts only on genuine price drops.

![n8n Workflow](images/n8n-workflow.png)

---

## 📊 Price History Storage
Google Sheets is used as a lightweight database to store historical prices for each product.

![Price History Sheet](images/price-history-sheet.png)

---

## 🧠 Price Drop Detection Logic
A price drop is detected using the condition:


