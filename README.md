* **Interactive Dashboard:** View the live project on [Tableau Public](https://public.tableau.com/views/RBI_ANALYTICS_MONA/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

* ## Case Study Presentation & Technical Artifacts

The full lifecycle of this analytics framework can be accessed directly using the quick links below:

* 📄 **[Business Requirements Document: Open Framework Strategy (BRD)](./Business%20Requirements%20Document%20RBI%20ANALYTICS.md)**  
  *The formal project strategy framework outlining the core banking challenges, user tracking personas, and system data governance protocols.*
* **[Executive Briefing Deck: Download Presentation Slides (PPTX)](./RBI_analytics_final_ppt.pptx)**  
  *A complete 4-slide presentation summarizing the business case, findings, database architecture, and performance logic.*
*  **[Database Architecture: View Star-Schema ER Diagram (PNG)](./RBI_ANALYTICS_STAR_SCHEMA_IN_SQL.png)**  
  *The physical entity-relationship model mapping the relational data warehouse connection vectors.*
* **[View Engineering: Open Database Schema (SQL)](./rbi_analytics_view_engineering.sql)**  
  *The ETL code script establishing our core database tables, dimensional normalization rules, and semantic view layers.*
*  **[KPI Summary: Open Queries (SQL Folder)](./SQL%20KPI)**  
  *The stored procedures, window functions, and aggregation query logic scripts.*

   ##  Raw Data Dictionary
* **`Deployment of Bank Credit by Major Sectors.xlsx`**: Macroeconomic historical data source tracking overall sectoral volume distributions across the 47 processed categories.
* **`RBI_ASSET_QUALITY_RAW.xlsx`**: Core underlying dataset tracking volumetric performance variations used to compute timeline growth velocity.



### RBI Sectoral Credit Allocation & Financial Performance Dashboard

An institutional-grade, interactive analytics dashboard engineered in Tableau to analyze the Reserve Bank of India (RBI) sectoral banking credit deployment and Year-over-Year (YoY%) growth metrics from 2018 to 2026. This project serves as an executive-level portfolio piece tracking macroeconomic credit risk and deployment patterns. 

###  Business Problem Solved: Mitigating Portfolio Concentration & Credit Risk
 ## Key Analytical Insights
Based on the integrated SQL metrics and interactive matrix validations, the portfolio surfaces three primary macroeconomic trends between 2018 and 2026:

* **The 2026 Credit Squeeze:** Total credit deployment shows a sharp deceleration in volume growth going into the final 2026 window. This suggests a macro-level tightening of bank lending criteria across major industrial segments.
* **Priority Sector Shifts:** By filtering through the "Lending Type" control, the data reveals that Priority Sector Lending (PSL)—specifically housing and small enterprise allocations—remained resilient even when standard commercial corporate credit flatlined.
* **Concentration Risks:** A deep dive into the Top 10 cohort matrix shows that the bulk of India's banking credit remains heavily concentrated within three core asset classes, making the overall portfolio highly sensitive to systemic shocks in those specific industries.


###  Core Features & UI Layout

The production-ready dashboard is structured to support rapid executive-level scanning via a balanced grid layout: 

* **Executive KPI Metric Block:** High-impact metric card rendering the **Total Credit** volume figure globally.
* **Asset Allocation Heatmap (Top Right):** A horizontal ranking chart evaluating relative credit weights across sectors, applying a high-contrast color gradient to highlight dominant risk categories.
* **Macro Credit Trends & YoY% Growth (Bottom Left):** An advanced **Dual-Axis Combination Chart** plotting absolute credit volumes against a calculated percentage trajectory line.
* **Financial Performance Matrix (Top Left):** A granular, multi-dimensional tabular text grid delivering exact historical valuations across reporting intervals.

###  Tech Stack & Data Engineering Workflow

### 1. Database Engineering & Optimization (MySQL)
* **Relational Schema Design:** Engineered a high-performance **Star Schema** directly inside MySQL, structurally isolating master dimensional tables from central transactional logs.
* **Query Acceleration via Indexing:** Created B-Tree indexes on all core Foreign Keys (`Metric Sector Id`, `Time Id`) across the fact and dimension tables, dramatically reducing join query latency for large reporting datasets.
* **Abstraction Layers via Views:** Developed specialized relational database **Views** to abstract raw source complexity, join structured dimensions, and pre-aggregate complex attributes into a clean, flat schema optimized for high-speed downstream BI consumption.

### 2. Fine-Tuning & Extraction (Power Query)
* Connected Power Query directly to the engineered MySQL database views.
* Sanitized remaining string attributes, parsed specialized calendar periods, and validated data types to ensure zero data ingestion gaps.

### 3. Business Logic & Interactivity (Tableau)
* Connected Tableau to the refined dataset, establishing seamless relationship cardinalities.
* Built responsive **Action Filters** across components, enabling stakeholders to dynamically slice the entire canvas by clicking asset bars.
* Implemented advanced table calculations to compute YoY% Growth Rates and relative allocation splits over time.
* **Automated Executive Reporting (Top Right):** Integrated dedicated UI export buttons for **PDF and PowerPoint (PPT)** formats. This feature enables senior stakeholders to instantly capture current filtered analytical views and download them as presentation-ready static slides for credit committee briefings and risk review meetings.




##  Dashboard Preview

RBI Sectoral Credit Dashboard Preview<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/785295ba-2edc-409b-b2bf-a436099fdf14" />




