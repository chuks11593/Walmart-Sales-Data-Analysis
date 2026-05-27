# Walmart-Sales-Data-Analysis

## 📌 Project Overview
This project delivers an end-to-end data analysis pipeline evaluating retail transactions from a dataset of 10,000 sales records. The goal of this analysis is to audit financial data, identify high-performing product categories, examine transaction patterns, and deliver an interactive dashboard for executive decision-making.

The project demonstrates a full analytical workflow using three core industry tools:
1. **SQL** for initial data extraction and baseline business aggregations.
2. **Python (Pandas)** for data quality auditing, feature engineering, and deeper statistical exploration.
3. **Tableau** for dynamic data visualization and business quadrant analysis.

---

## 🔧 Tech Stack & Tools
* **Database Language:** SQL
* **Programming Language:** Python 3.x
* **Libraries Used:** Pandas, NumPy
* **Data Visualization:** Tableau Desktop / Tableau Public

---

## 📊 Methodology & Process

### Phase 1: Strategic Extraction (SQL)
Before diving into heavy cleaning, I utilized SQL queries to aggregate raw transactional records and establish baseline operational metrics:
* Calculated total revenue and profitability metrics grouped by individual cities and branches.
* Isolated the top-performing product categories ranked by total item volume sold.
* Extracted date parts to evaluate monthly transaction trends and check for potential operational seasonality.

### Phase 2: Data Auditing & Transformation (Python)
Using Jupyter Notebook and the Pandas library, I performed data quality checks and engineered new metrics to deepen the analysis:
* Audited the dataset for missing data, structural anomalies, and incorrect data types.
* **Feature Engineering:** Programmatically derived a `Total_Cost` field across all 10,000 rows utilizing the standardized profit margins:
  $$Total\_Cost = (UnitPrice \times Quantity) \times (1 - ProfitMargin)$$
* Leveraged vectorised groupings to analyze how payment types (Cash, Credit Card, E-wallet) correlate with average checkout values and customer satisfaction scores.

### Phase 3: Executive Visualisation (Tableau)
The final stage translated numerical findings into an interactive, visual business asset. 
* Developed high-level KPI cards tracking **Total Revenue**, **Units Sold**, and **Average Customer Ratings**.
* Designed a dynamic sales trend chart and geographical distribution visual.
* **Key Feature - Sales vs. Profit Margin Quadrant Analysis:** Built a specialized scatter plot mapping product revenue against average profit margins. This visual reveals that while profit margins are highly standardized across all categories (~39%), a massive volume disparity exists—identifying *Fashion Accessories* as the primary revenue engine ($500k+) and highlighting *Electronic Accessories* as a low-volume growth opportunity.
### Advanced Dashboard Feature: Interactivity & Dynamic Filtering
To transform this from a static report into an active business discovery tool, I implemented **Dashboard Action Filtering ("Click-to-Filter")**:

* **The Feature:** The regional performance visuals ( Bar Charts) are configured to act as global dashboard filters.
* **How it Works:** By enabling the "Use as Filter" (funnel icon) control on the geographical containers, clicking any specific city data point (such as *Plano* or *San Antonio*) triggers an instant client-side recalculation.
* **The Result:** The entire dashboard—including the product tree maps, time-series line trends, and high-level KPI totals—instantly updates in real-time to isolate the metrics of the selected city, allowing stakeholders to drill down from macro-trends to micro-insights seamlessly.
---

## 📈 Key Insights & Business Takeaways
* **Standardized Margins:** Profit margins are perfectly consistent at approximately 39% across all product lines. Because margin percentages are locked, bottom-line profit growth relies entirely on driving sales volume.
* **The Revenue Driver:** *Fashion Accessories* significantly outperforms all other sectors, proving to be the business's anchor product category.
* **Volume Opportunity:** *Electronic Accessories* maintains a healthy 39% margin but suffers from low sales volume (under $100k). Strategic marketing interventions should target this sector to push its revenue placement further to the right.

---

## 🚀 How to View the Project
* **SQL Scripts:** Check the `/sql` directory for the extraction queries.
* **Python Notebook:** View `walmart_analysis.ipynb` for the full data cleaning and transformation code.
* **Interactive Dashboard:** https://public.tableau.com/views/walmartanalysistableauoriginal/Dashboard1
