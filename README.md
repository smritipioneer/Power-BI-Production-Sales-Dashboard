# Power-BI-Production-Sales-Dashboard
This project demonstrates how to design a **Star Schema data model** and build an interactive **Production &amp; Sales Dashboard** in Power BI.   The dashboard provides insights into **Revenue, Profit, Units Sold, Stock on Hand, and Store Count**, using **DAX time intelligence functions** for advanced KPI analysis.
# Power BI Production & Sales Dashboard

<img width="1119" height="472" alt="image" src="https://github.com/user-attachments/assets/de46acf7-f6dd-435a-931b-b4fee6d82f97" />

## Objective
This project demonstrates how to design a **Star Schema data model** and build an interactive **Production & Sales Dashboard** in Power BI.  
The dashboard provides insights into **Revenue, Profit, Units Sold, Stock on Hand, and Store Count**, using **DAX time intelligence functions** for advanced KPI analysis.

---

## Data Model
The project uses a **Star Schema** with the following tables:

- **Calendar** → Date dimension for time intelligence  
- **Sales** → Transaction facts (Units, Date, Product_ID, Store_ID)  
- **Products** → Product attributes (Category, Cost, Price)  
- **Stores** → Store attributes (City, Location, Open Date)  
- **Inventory** → Stock on hand per product/store  

![Star Schema]

<img width="971" height="486" alt="image" src="https://github.com/user-attachments/assets/7cc7d2b6-f955-4ce9-82b7-c982dabb7484" />

---

## 📈 Key KPIs
- **Revenue YTD**
- - **Revenue YTD**  
  ```DAX
  Revenue YTD = TOTALYTD([Total Revenue], Calendar[Date])
- - **Profit LY**  
  ```DAX
  Profit LY = CALCULATE([Total Profit], SAMEPERIODLASTYEAR(Calendar[Date]))
- - **Revenue Growth %**  
  ```DAX
  Revenue Growth % = DIVIDE([Total Revenue] - [Profit LY], [Profit LY])
 - - **other KPI %**
   - Units Sold, Stock on Hand, Store Count
  
## Dashboard Features
KPI Cards for quick insights

Slicers for Year, Product Category, Store filters

Line Chart for Revenue YTD vs Last Year trends

Matrix for monthly breakdown

Donut Chart for category share of units sold

🛠️ DAX Highlights
DAX
Total Revenue = SUMX(Sales, Sales[Units] * RELATED(Product[Price]))
Total Profit = SUMX(Sales, (Sales[Units] * RELATED(Product[Price])) - (Sales[Units] * RELATED(Product[CostPerUnit])))
🚀 How to View
Download the .pbix file from the pbix_file/ folder.

Open it in Power BI Desktop (free download from Microsoft).

Explore the dashboard with slicers and visuals.

Alternatively, view screenshots in the screenshots/ folder.



📂 Repository Structure
Code
📂 PowerBI-Production-Dashboard
 ┣ 📂 screenshots
 ┃ ┗ dashboard_overview.png
 ┣ 📂 data_model
 ┃ ┗ star_schema.png
 ┣ 📂 pbix_file
 ┃ ┗ ProductionDashboard.pbix
 ┣ 📄 README.md

💡 Skills Demonstrated
Data Modeling (Star Schema design)

DAX (Time intelligence: YTD, LY, Growth %)

Visualization (KPI cards, slicers, charts, matrix)

Business Insight (Production & sales performance analysis)
  

  
  ```DAX
  Revenue YTD = TOTALYTD([Total Revenue], Calendar[Date])
