# MusembiPrince-PowerBI_Practical_Exam_-Prince_RM_958-
Final Bi practical exam

## **1. Overview**

This project uses the **AdventureWorks dataset** to design an interactive Power BI report showcasing sales, profitability, and performance trends. The report includes KPIs, trend charts, decomposition trees, gauges, and custom visuals to provide actionable business insights.

## **2. Approach**

1. **Data Preparation**

   * Loaded AdventureWorks data into Power BI.
   * Performed data cleaning and transformation using Power Query (e.g., removed null values, adjusted data types, created calculated columns for Profit, Profit Margin, and Budget).
     - **dax snippets and data images(applied steps on the right of the images)**
       = Table.AddColumn(#"Expanded Product_data", "Profit", each [Sales Amount]- ([Order Quantity] * [Standard Cost]))
       = Table.AddColumn(#"Added Custom", "Sales Category", each if [Sales Amount] > 1000 then "High"
else if [Sales Amount] >= 500 then "Medium"
else "Low")
= Table.SelectRows(#"Added Custom1", each [OrderDateKey] >= 20180101)
= Table.AddColumn(#"Filtered Rows", "IsOutlier", each if [Sales Amount] > 5000 then "Outlier" else "Normal")

       <img width="846" height="340" alt="image" src="https://github.com/user-attachments/assets/1ae6ae0d-ca86-4ffe-829c-aff91a695229" />

        <img width="842" height="331" alt="image" src="https://github.com/user-attachments/assets/2fa2005c-6888-49a5-9783-0435b7f5d856" />
        
        <img width="838" height="332" alt="image" src="https://github.com/user-attachments/assets/a5ede4af-cee5-4868-9326-f349d504108f" />

        <img width="844" height="328" alt="image" src="https://github.com/user-attachments/assets/62e3e53d-166d-4423-8903-c83dc30eaca5" />

        <img width="848" height="314" alt="image" src="https://github.com/user-attachments/assets/790f30b7-3df3-4492-8d16-11b11e419afd" />

        <img width="850" height="330" alt="image" src="https://github.com/user-attachments/assets/fea78b73-50bf-44b8-b554-210236ad5732" />

        <img width="850" height="302" alt="image" src="https://github.com/user-attachments/assets/73cb2aeb-f02d-4915-93b4-5559d8f71d1d" />




2. **Data Modeling**

   * Established relationships between fact and dimension tables (Sales, Customers, Products, Territories, Dates).
     **schema**
     <img width="539" height="376" alt="image" src="https://github.com/user-attachments/assets/1e4066ca-9f70-4a0c-84f6-c3ed73c8bbb2" />
     **relationships**
     <img width="603" height="378" alt="image" src="https://github.com/user-attachments/assets/707c56a0-5da0-49bd-9425-a330491c21e8" />


   * Created hierarchies (e.g., date).
     <img width="190" height="120" alt="image" src="https://github.com/user-attachments/assets/6676397b-8c65-4049-87c6-1be9dbe4a776" />
     <img width="180" height="129" alt="image" src="https://github.com/user-attachments/assets/e62d7cf7-4009-421f-99f9-74944b190df3" />


3. **Measure Creation**

   * Developed DAX measures for KPIs:

 <img width="174" height="211" alt="image" src="https://github.com/user-attachments/assets/aa3b7733-79d4-4a43-ad6a-723742bd2c6d" />

4. **Visual Development**

   * Designed KPI Cards, Gauge charts, Decomposition Trees, pie charts, bar graphs, line graphs and custom Bullet Charts from the Power BI Marketplace.
     <img width="218" height="36" alt="image" src="https://github.com/user-attachments/assets/4b92e1bd-d438-4e23-99ac-f2ef44459b04" />
     <img width="103" height="89" alt="image" src="https://github.com/user-attachments/assets/0e3a7169-b9e4-4c39-9420-50904685f5e2" />
     <img width="260" height="201" alt="image" src="https://github.com/user-attachments/assets/a217284c-f01d-4999-9342-20ab1e5ce98d" />
     <img width="285" height="154" alt="image" src="https://github.com/user-attachments/assets/423a2525-34d6-40f9-b259-e117ffdd96e5" />
     <img width="403" height="226" alt="image" src="https://github.com/user-attachments/assets/d14098fd-43e9-4a03-9995-eeb7c484afa5" />
     <img width="247" height="119" alt="image" src="https://github.com/user-attachments/assets/78e878ca-5cb3-4536-a4ac-34cd71ae5359" />
     <img width="256" height="159" alt="image" src="https://github.com/user-attachments/assets/44f2e6b4-f0aa-4585-ac3f-9b3cb7b43b5e" />
     <img width="110" height="90" alt="image" src="https://github.com/user-attachments/assets/57f0831c-987f-4493-bc1a-0e37e204ef51" />
     <img width="295" height="53" alt="image" src="https://github.com/user-attachments/assets/af7cab61-13a1-48fc-b410-3b7ef404192b" />










## **3. Challenges & Solutions**

| **Challenge**                                                   | **Solution**                                                                                  |
| Missing or inconsistent data in some AdventureWorks tables      | Used Power Query filters, transformations, and data profiling to clean and standardize values |
| Target values in Gauge visuals require fields, not manual input | Created separate DAX measures for profit margin and profit margin Target thresholds                             |
| Large dataset relationships caused performance lag              | Implemented star schema modeling and optimized DAX calculations                               |

## **4. Dashboard Report Screenshot**


### **Budget and profit analysis Dashboard**
<img width="660" height="377" alt="image" src="https://github.com/user-attachments/assets/2df3c1d4-131d-4426-9151-8476bbf62960" />

### **sales overview Dashboard**
<img width="656" height="374" alt="image" src="https://github.com/user-attachments/assets/a75333cd-11fb-42c0-bc7a-7c1374766fc4" />

### **product analysis dashboard**
<img width="655" height="368" alt="image" src="https://github.com/user-attachments/assets/8f9c4a92-d47c-4b8b-b866-e39ce064899f" />

### **customer analysis dashboard**
<img width="661" height="375" alt="image" src="https://github.com/user-attachments/assets/3267e29d-082e-4dbc-9717-21a0fb420ae8" />



## **5. Key Insights**

### **Budget & Profit Analysis Dashboard Insights**
1. **Performance Gap**  
   * Sales are at $373K (9.09% below $410K target)  
   * Profit margin at 10.9% (significantly below 30% target)  
 

2. **Regional Distribution**  
   * Order of concentration: North America > Europe > Asia  
   * Underperforming regions: Africa, South America, Atlantic Ocean  
   - *Opportunity for regional expansion strategies*


### **Sales Overview Dashboard Insights**

1. **Performance vs Target**
- **Current Sales**: $373.02K
- **Target**: $410.32K → **Shortfall** of **9.09%**, indicating underperformance.

2. **Sales Trends**
- **Monthly Sales (2018–2020)**: Fluctuating trend, suggesting seasonal or campaign-driven spikes.

3. **Category Breakdown**
- **Bikes dominate** with **$83.36M** (85.17% of total sales).
- **Components** follow at **$11.18M** (11.43%).
- **Clothing & Accessories** contribute marginally.

4. **Regional Insights**
- **Order Quantity by Region**: Highest in **North America**, followed by **Europe** and **Australia**.
- **Total Sales by Country/Region**:
  - **United States**: ~4T
  - **Canada, France, UK, Germany, Australia**: Significantly lower
    

### Summary Metrics
- **Total Sales**: 11.35T
- **Running Total Sales**: 97.88M
- **Order Quantity**: 262,740
- **Avg Sales per Customer**: $5,354.23
- **Total Customers**: 18,281
- **Total Product Sales**: $87.21M


### **Product Analysis dashboard**:

1. **Sales by Individual (Tree Map)**
- Named contributors (e.g., Ian, Kaitlyn, Chloe) each contribute around **$120K**
  
2. **Sales by Product**
- **Top Product**: “Touring-3...” leads with over **$1.2M** in sales.
- Other products trail significantly, indicating a strong product concentration.

3. **Profit Distribution**
- **Highest Profit**: ~$793.9K (6.94%)
- **Lowest Profit**: ~$24.78K (0.22%)
- Profit is unevenly distributed, with a few products driving most of the margin.

4. **Sales by Category**
- **Bikes** dominate again, consistent with the Sales Overview dashboard.
- **Components** (Com...) are secondary, with other categories not clearly visible.

### **Customer Insights Dashboard Insights**

1. **Customer-Level Sales & Profit**
- **Top Contributor**: `[Not Applicable]` with **$5.55T** in sales and **203,543** orders — likely a placeholder or unclassified customer.
- Named customers (e.g., Aaron Adams, Aaron Alexander) show much smaller sales volumes, typically under **$500M**.
- **Profit Distribution**: Highly skewed — `[Not Applicable]` drives the bulk of the **$10.67M** total profit.

1. **Category Breakdown**
- **Sales by Category**:
  - **Bikes** dominate again.
  - **Components, Clothing, Accessories** trail behind.
- **Customer Distribution**:
  - **Bikes**: 48.03%
  - **Clothing**: 28.99%
  - **Accessories**: 22.18%
  - **Components**: Minimal

2. **Top 5 Product Sales**
- All top products are **Mountain-200** variants (Black/Silver, sizes 38–46).
- Combined sales: **$97.88M**, indicating strong product concentration.

3. Budget vs Sales
- **Total Sales**: $97.88M
- **Budget**: $104.65M → Slight **underperformance** relative to budget.

### Summary Stats
- **Total Sales**: 11.35T
- **First Country**: Australia
- **Total Customers**: 18,281
- **Avg Sales per Customer**: $5,354.23
- **Profit Margin**: $72.39M


## **6. Assumptions & Limitations**

* **Budget** is assumed to be **1.2 × Cost** for all products.
* Forecasts assume a **linear growth trend** without external market influences.
* Some product categories have incomplete historical data, affecting YoY comparisons.

  ## **7. RLS**
<img width="776" height="363" alt="image" src="https://github.com/user-attachments/assets/38a45957-bf1d-4984-a184-37b1262abed6" />
<img width="242" height="132" alt="image" src="https://github.com/user-attachments/assets/2bdf3177-17ab-465f-b786-12a0d7936d23" />





