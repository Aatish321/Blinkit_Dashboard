
## 📊 BLINKIT | SALES & CUSTOMER REPORT

### 🔗 Dashboard Preview  
This Power BI dashboard helps visualize Blinkit's key sales and customer insights, allowing for dynamic interactions, drill-downs, and performance monitoring.

---

## 📌 Problem Statement  
The main goal of this dashboard is to provide a clear understanding of sales performance, customer behavior, and product-wise trends for Blinkit operations across cities in India.

This dashboard allows stakeholders to:
- Track **net sales**, **repeat customers**, and **total orders**.
- Monitor **retention KPIs** like repeat rate, purchase frequency, and lifetime value.
- Explore **region-wise sales** using map visuals.
- Evaluate performance by **payment method**, **rating**, and **product category**.
- Drill into each chart to explore **detailed datasets** and export them.

---

## 🛠️ Steps Followed

### Step 1: Data Loading  
- Imported multiple CSVs into Power BI Desktop including city-level transactional data.

### Step 2: Data Preparation  
- Cleaned & transformed data using Power Query Editor.
- Created necessary relationships among location and transaction columns.

### Step 3: Dynamic Titles for Visualization  
Created a dynamic heading measure using DAX to reflect user selection:

```dax
Dynamic Title = 
IF('Select Measure'[Select Measure Order]= 0,"Net Sales",
  IF('Select Measure'[Select Measure Order]= 1, "Repeat Customer",
    IF('Select Measure'[Select Measure Order]= 2,"Total Quantity",
      IF('Select Measure'[Select Measure Order]= 3,"Total Customers", "other"
))))
```

### Step 4: Select Measure Table for KPI Switching  
Created a parameter-like table to allow KPI switching dynamically:

```dax
Select Measure = {
    ("Net Sales", NAMEOF('Worksheet'[Net Sales]), 0),
    ("Repeat Customers", NAMEOF('Worksheet'[Repeat Customers]), 1),
    ("Total Quantity", NAMEOF('Worksheet (4)'[Total Quantity]), 2),
    ("Total Customers", NAMEOF('Worksheet (3)'[Total Customers]), 3)
}
```

### Step 5: KPI Cards and Metrics  
- Created multiple **measures** to compute:
  - Lifetime Value
  - Repeat Rate
  - Purchase Frequency
- These KPIs are visualized as cards for easy monitoring.

### Step 6: Drill Through Feature  
- Enabled **drill-through** from each visual, allowing users to:
  - Navigate to a detailed dataset view
  - Download filtered datasets from the chart's context

### Step 7: Color Palette and Branding  
- Used brand colors of Blinkit:
  - Primary Yellow: `#FFD54F`
  - Green tones: `#1B5E20`, `#256D29`, `#2E7C33`, `#388E3C`
  - Created consistent **theme styling** for charts and slicers.

### Step 8: Interactive Visuals  
- Added interactive slicers for:
  - Area
  - Measure Selection
- Used **Donut Charts** for payment method and rating distribution.

---

## 📷 Sample Dashboard Preview

![dashboard (2)](https://github.com/user-attachments/assets/61117653-dc0f-4125-b892-ffabbb60deab)




---

## ✅ Key Features

- 🔁 Dynamic titles based on user input
- 📈 Drill-through reports with export capabilities
- 🟨 Fully branded color scheme in Blinkit theme
- 📊 Clean layout covering transactional, behavioral, and product data
- 📌 Slicers and measures for user interactivity
