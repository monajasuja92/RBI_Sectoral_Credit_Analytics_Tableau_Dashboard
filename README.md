* **Interactive Dashboard:** View the live project on [Tableau Public](https://public.tableau.com/views/RBI_ANALYTICS_MONA/BankingOperationsview?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

* ## Case Study Presentation & Technical Artifacts

The full lifecycle of this analytics framework can be accessed directly using the quick links below:

* 📄 **[Business Requirements Document: Open Framework Strategy (BRD)](https://github.com/monajasuja92/RBI_Sectoral_Credit_Analytics_Tableau_Dashboard/blob/main/Business%20Requirements%20Document%20RBI%20ANALYTICS.pdf)**  
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

###  Project Case Study: Turning Messy Central Bank Tables into Actionable Risk Insights
1. The Real-World Banking Problem Solved
 The data is released in wide, disconnected yearly tables. Even worse, the files contain an analytical trap: they mix completely different financial metrics together. Half of the data is calculated as a % of customer bank deposits (which matters for internal bank liquidity), while the other half shifts mid-row to a % of the country’s GDP (which matters for macroeconomics).If an analyst charts these raw rows side-by-side, it creates an optical illusion that leads to massive calculation errors. Because fixing this manually in Excel takes days, executive leadership historically received risk reports long after the data became public, destroying their ability to react quickly to market shifts.
2. How We Solved It (The Engineering Strategy)To fix this friction, we bypassed manual data cleanup and built a programmatic, automated pipeline:The Relational Model (Star Schema):
    We broke down the messy sheets into an organized backend database consisting of a centralized Fact Table connected to distinct Time and Sector Dimensions. This allows the data to scale seamlessly without duplicate rows or mapping errors.
   The "Boundary Wall" Math Rule:
   Inside Tableau, we engineered smart, conditional logic formulas to separate the overlapping percentages. By establishing a numeric boundary threshold, the system automatically routes high metrics (over 65%) into a Banking Liquidity View and low metrics into a Macro GDP View.
   The Two-Page App Interface: We built an interactive dashboard equipped with top navigation buttons. It splits the conflicting visual metrics onto two separate tabs so executives can switch between internal bank health and the broader economy in under 5 seconds.
3. Key Financial Insights DiscoveredBy cleaning up the 9-year historical horizon (2018–2026), our interactive visualizations revealed critical economic trends:The 2026 Credit Slowdown:
   While absolute lending volume appears massive, our dual-axis velocity line reveals a sharp deceleration heading into 2026. This indicates that banks heavily tightened their lending criteria, pulling back on risk.Priority Lending as a Safe Haven: By filtering through the global controls, we discovered that government-mandated Priority Sector Lending (PSL)—especially housing and small enterprise allocations—remained incredibly stable and resilient even during economic phases when standard commercial corporate credit flatlined.
   The Systemic Debt Footprint:
    Our macro view exposed a long-term 54.61% Average Credit-to-GDP Share. This reveals exactly how deeply the broader Indian economy depends on commercial bank credit to fuel its annual GDP growth.
 4. Professional Analyst Recommendations
      Based on these insights, an analyst would deliver the following strategic recommendations to bank leadership:
      Implement a Micro-Sector Alert Trigger: Because credit velocity slowed down heavily in 2026, the risk team should configure automated color-shaded indicators on our Performance Matrix to immediately red-flag any micro-sectors showing consecutive reporting gaps.
      Optimize Risk Appetite via Safe Assets: Since bank investments are heavily tied up in risk-free government bonds, leadership should utilize our dashboard's asset-split charts to identify when to safely rotate capital into high-yield corporate debentures as macro growth starts to recover.
      Automate the Data Pipeline Structure: To completely eliminate manual overhead, this dashboard should be connected to an automated scraper script that instantly pushes new annual RBI data batches straight into our Fact table schema the moment they are published.

###  Core Features & UI Layout
To resolve the data split problem, the user interface is structured as an interactive, two-page corporate application layout. By maintaining identical font hierarchies, right-hand filter panels, and a dark top navigation bar, both dashboards feel like a unified, professional software system.

Dashboard Page 1:
Banking Operations & Liquidity ViewThis view focuses entirely inward on internal banking health, charting metrics calculated strictly as a percentage of customer deposits.Executive Summary Cards (Top Left): Displays two prominent metrics—the 1.95B Total Systemic Value and a unique count of 47 Active Reporting Sectors—giving leadership an immediate snapshot of data scale.Dual-Axis Growth Trend (Center Left): Combines absolute loan volumes (Bars) against yearly growth speed (Line). This layout allows risk teams to instantly see that while total volume is high, the actual speed of growth plummeted to -84.2% heading into 2026.Dynamic Performance Matrix (Bottom Grid): A comprehensive grid showing exactly how many rows of data exist per sector. It uses a clean tabular format to act as a visual data auditor for reporting completeness.

Dashboard Page 2:
Macroeconomic GDP ViewThis view shifts focus entirely outward, tracking how bank lending impacts the broader country using metrics calculated as a percentage of national GDP.Macro Exposure Scorecard (Top Left): Features a large, bold KPI block displaying the long-term 54.61% Average Credit-to-GDP baseline to track overall market leverage.GDP Horizon Trend Lines (Center Canvas): Clean, separate time-series bar and line charts tracking credit and investment shares. Because the numbers sit below our custom 22.0% filtering boundary wall, Tableau plots them safely without overlapping text.Regulatory PSL Share Chart (Top Right): An interactive pie chart that cleanly isolates government-mandated Priority Sector Lending (0.11B) away from standard commercial lending blocks (1.84B), satisfying compliance workflows instantly.Global Interaction Sidebar (Far Right): Houses the dark web application Navigation Toggle alongside synchronized Lending Type checkboxes so that a filter clicked on Page 1 automatically updates the visuals on Page 2.
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




