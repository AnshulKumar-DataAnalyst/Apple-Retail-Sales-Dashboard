# 🍎 Apple Retail Sales Dashboard — Power BI

![Power BI](https://img.shields.io/badge/Tool-Power%20BI-F2C811?logo=powerbi)
![Analytics](https://img.shields.io/badge/Project-Data%20Analytics-red)

A multi-page interactive Power BI dashboard analyzing Apple's global retail sales data across products, stores, and markets from 2020 to 2024.

---

## 📌 Project Overview

This dashboard was built to answer one question: **Where is Apple's revenue coming from — and where is it slipping?**

It covers 5 years of sales data across 75 active stores, 88 products, and multiple countries — broken down into 4 focused report pages with year-on-year comparisons, product-level intelligence, and global store performance.

---

## 🖥️ Dashboard Pages

### 🏠 Home Page
<img src="Screenshots of Dashboard/1.png" width="50%">

A clean navigation page with a summary of all 4 report sections — designed so any viewer can jump directly to what they need.

---

### 📊 Executive Summary
<img src="Screenshots of Dashboard/2.png" width="50%">
**What's shown:**
- 4 KPI cards: Total Revenue, Total Transactions, Average Order Value, Total Units Sold — each with YoY % change vs previous year
- Monthly Revenue Trend with CY vs PY overlay (area + dotted line)
- Revenue by Year bar chart (2020–2024)

**Key Insight (2024):**
- Total Revenue dropped to **$1.10B** — down **12.68%** vs 2023
- Transactions fell **13.08%** and Units Sold dropped **12.89%**
- Average Order Value slightly increased by **0.45%** — showing pricing held up even as volume declined
- **November shows a sharp revenue cliff** — dropping to ~$42M, which is the most critical signal in the entire dashboard

---

### 📈 Sales Performance
<img src="Screenshots of Dashboard/3.png" width="50%">

**What's shown:**
- Revenue by Month line chart with month-on-month % change labels
- Revenue by Quarter: CY vs PY grouped bar chart
- Country slicer to filter all visuals

**Key Insight (2024):**
- Revenue stayed relatively flat Jan–Oct (~$100M–$109M range)
- **November collapsed by 61.61%** to $41.82M — a major outlier that needs business explanation (incomplete data, seasonal gap, or reporting issue)
- Q4 CY Revenue ($0.15bn) vs PY Revenue ($0.32bn) — a dramatic gap showing Q4 2024 severely underperformed Q4 2023

---

### 📦 Product Intelligence
<img src="Screenshots of Dashboard/4.png" width="50%">

**What's shown:**
- Total Products: 88
- Top Product Revenue KPI with product name
- Revenue by Category donut chart (8 categories)
- Top 10 Products table with **actual product images**, CY Revenue, Units Sold, and YOY% Growth

**Key Insight (2024):**
- **Tablets lead at 15.56%** of total revenue, followed by Accessories (15.03%) and Smartphones (13.97%)
- **iMac 27-inch** is the top revenue product at $2.14M but shows **-14.85% YOY decline**
- Every product in the Top 10 shows negative YOY growth in 2024 — confirming this is a market-wide decline, not product-specific
- iPad 9th Generation (previously top product in 2023) dropped to 8th position

---

### 🌍 Store & Market Analysis
<img src="Screenshots of Dashboard/5.png" width="50%">

**What's shown:**
- Top Country by Revenue KPI (United States — $1.10B)
- Bubble map: Revenue by country (bubble size = total revenue)
- Top 10 Stores by Revenue horizontal bar chart
- Active Stores count: 75

**Key Insight (2024):**
- **Apple Chadstone** (Australia) tops the store list at $29.96M — overtaking Dubai Mall which led in 2023
- UAE, UK, and Australia stores consistently appear in the top rankings
- The US dominates overall revenue but individual store rankings are led by international locations
- Store revenue gap is visible: Top stores earn ~$29–30M while stores ranked 7–10 earn ~$15–16M

---

## ⚙️ What I Built & How

| Feature | Approach |
|---|---|
| CY vs PY comparison | DAX measures using `MAX(Year)` and `ALL()` pattern |
| YOY % change | Calculated column with conditional arrow formatting |
| Product images in table | Base64 encoded images loaded via Power Query |
| Year slicer buttons | Bookmark + button navigation |
| Bubble map | Bing Maps visual with country-level aggregation |
| Monthly % change labels | Data labels with custom DAX measure |
| Color-coded KPI cards | Conditional formatting on measure values |

---

## 🧩 Challenges Faced & How I Solved Them

**1. YOY% showing wrong values**
The measure was picking up the wrong base year when slicers were active.
→ Fixed by using `CALCULATE(..., ALL(Date[Year]))` with `MAX(Date[Year]) - 1` as the PY reference.

**2. Product images not loading in the table**
Images weren't rendering inside the matrix visual.
→ Solved by converting product images to Base64 strings via Python (Google Colab) and loading them through Power Query as image URLs.

**3. November 2024 data cliff**
Sales dropped 61% in November — initially looked like a dashboard error.
→ Confirmed it's a dataset issue (partial month data for Nov 2024), not a DAX bug. Added it as an insight rather than hiding it.

**4. Consistent theme across 4 pages**
Keeping colors, fonts, and card styles identical across all pages manually was time-consuming.
→ Built a custom theme JSON and applied it globally, then only adjusted per-visual formatting where needed.

---

## 🛠️ Tools Used

- **Power BI Desktop** — Dashboard development
- **Power Query** — Data transformation & Base64 image loading
- **DAX** — KPI measures, YOY calculations, conditional formatting
- **Python (Google Colab)** — Image download & Base64 conversion
- **Microsoft Bing Maps** — Geographic bubble map

---

## 📁 Dataset

- Source: Simulated Apple Retail Sales dataset
- Years covered: 2020–2024
- Scope: 75 stores, 88 products, global markets

---

## 🔗 Connect

| | |
|---|---|
| 💼 LinkedIn | [linkedin.com/in/anshul-kumar-dataanalyst](https://www.linkedin.com/in/anshul-kumar-dataanalyst) |
| 🌐 Portfolio | [AnshulKumar-DataAnalyst.github.io](https://AnshulKumar-DataAnalyst.github.io) |
| 💻 GitHub | [github.com/AnshulKumar-DataAnalyst](https://github.com/AnshulKumar-DataAnalyst) |
| 📧 Email | anshul_kumar12@outlook.com |

---

> *Built as part of my Data Analytics portfolio. Feedback welcome — drop a comment or connect on LinkedIn!*
