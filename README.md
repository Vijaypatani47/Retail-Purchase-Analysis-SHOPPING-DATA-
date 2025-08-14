# Retail Purchase Analysis – Power BI Dashboard

An interactive **Power BI** dashboard that analyzes retail purchases across the U.S., featuring KPIs, seasonal trends, category mix, payment behavior, demographics, and geography. Built for quick decision-making with clean visuals and business-friendly measures.

![Dashboard Screenshot](./assets/retail-purchase-analysis.png) <!-- replace with your image path -->

---

## 🔍 Key Highlights

- **Total Revenue:** 233K  
- **Total Orders:** 3.9K  
- **Avg CSAT (Customer Satisfaction):** 3.75  
- **Avg Visits:** 25.35  

### What you can explore
- **Geo view:** Total purchase value by location (map)
- **Seasonality:** Trend across Fall, Spring, Winter, Summer
- **Category mix:** Clothing, Accessories, Footwear, Outerwear
- **Demographics:** Age group contributions & subscription status by gender
- **Payments:** Transaction volume by method (Credit Card, Venmo, Cash, PayPal, Debit, Bank Transfer)
- **Top items:** Top 5 purchased items by value

### Slicers/Filters
`Payment_Method`, `Shipping_Type`, `Discount_Applied`, `Item_Name`, `Subscription_Status (Yes/No)`, and **Season buttons** (Fall, Spring, Summer, Winter).

---

## 📊 Actionable Insights (from current snapshot)

- **Category leader:** Clothing contributes **~44.6%** of revenue (≈104K of 233K).  
  - _Focus_: Keep inventory depth and promos; bundle with Accessories (2nd at ~31.7%).  
- **Seasonality:** Revenue dips slightly in **Summer (~55.8K)** vs **Fall (~60K)**.  
  - _Action_: Summer-specific promotions or new arrivals to counter dip.  
- **Demographics:** **Female buyers ≈67.7%** of revenue (≈158K); Males ≈32.3%.  
  - _Action_: Targeted campaigns and collections for female segments; test offers for male growth.  
- **Age groups:** **46–60** is the highest-spending band (**≈68K**).  
  - _Action_: Tailor loyalty offers & messaging to mature shoppers; keep UX simple.  
- **Payments:** **Credit Card** leads (≈696 txns) but other methods are close.  
  - _Action_: Keep multi-pay options; negotiate CC fees; promote fastest checkout paths.  
- **Top items:** Blouse, Shirt, Dress, Pants, Jewelry dominate value.  
  - _Action_: Feature these in hero sections; bundle cross-sells from Accessories.

> Use slicers to validate if these patterns hold for specific items, discounts, or shipping types.

---

## 🧠 Project Goals

- Provide a **one-glance executive view** of sales health.
- Enable **self-serve analysis** with intuitive filters.
- Surface **seasonal opportunities** and **high-value cohorts**.

---

## 🗂️ Repository Structure

```
.
├─ Retail Purchase Analysis (SHOPPING DATA).pbix
├─ assets/
│  └─ retail-purchase-analysis.png   # dashboard screenshot (add your image)
├─ README.md
└─ LICENSE
```

---

## ⚙️ How to Use

1. **Download** the `.pbix` file.
2. Open in **Power BI Desktop** (latest version recommended).
3. If prompted for data sources, update the paths or credentials.
4. Interact with slicers and visuals to explore insights.

---

## 🧮 DAX (sample measures)

```DAX
-- Core KPIs
Total Revenue = SUM('Sales'[Revenue])

Total Orders = DISTINCTCOUNT('Sales'[OrderID])

Avg CSAT = AVERAGE('Sales'[CSAT])        -- if CSAT column exists (1–5)

Avg Visits = AVERAGE('Sales'[Visits])    -- if Visits column exists

-- Category Revenue
Category Revenue = SUM('Sales'[Revenue])

-- % of Revenue by Category
Category % of Revenue =
DIVIDE([Category Revenue], [Total Revenue], 0)

-- Year/Season Trend
Season Revenue = CALCULATE([Total Revenue], ALLSELECTED('Date'[Season]))
```

> Adjust table/column names to your schema if they differ.

---

## 🚀 Roadmap / Future Enhancements

- Add **RFM** segmentation & **CLV** estimate.
- Create a **cohort retention** view by subscription status.
- Include **discount effectiveness** and **shipping type** cost analysis.
- Drillthrough pages for **Product**, **Customer**, and **Region**.
- Bookmark-driven **story mode** for exec presentations.

---

## ✅ Requirements

- Power BI Desktop (Windows)
- Data files (embedded or external connections, depending on your model)

---

## 📜 License

This project is licensed under the **MIT License**. See `LICENSE` for details.

---

## 🙌 Credits

Designed & developed by **Vijay** (Data Analysis).  
Feel free to open issues or suggest enhancements!
