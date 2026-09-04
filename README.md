

### RBI Sectoral Credit Allocation & Financial Performance Dashboard

An institutional-grade, interactive analytics dashboard engineered in Tableau to analyze the Reserve Bank of India (RBI) sectoral banking credit deployment and Year-over-Year (YoY%) growth metrics from 2018 to 2026. This project serves as an executive-level portfolio piece tracking macroeconomic credit risk and deployment patterns. 

### 🎯 Business Problem Solved: Mitigating Portfolio Concentration & Credit Risk

In institutional banking, unmonitored capital concentration in a single sector exposes a financial firm to extreme systemic risk if that market undergoes a sudden downturn. This analytics framework solves two critical financial risk management issues: 

1. **Identifying High-Risk Concentration Risk:** The dashboard acts as an early-warning system by isolating exactly where credit lines are overly concentrated. For instance, it reveals that a massive portion of total credit is heavily exposed to the **Services** and **Personal Loan** sectors, signaling a high-beta consumer dependencies risk profile.
2. **Detecting Liquidity Inefficiencies via YoY% Volatility:** By mapping YoY% growth fluctuations directly over absolute deployment volumes, risk managers can instantly pinpoint asset categories experiencing destabilizing credit expansion or sudden contraction (such as the market inflection points seen in 2024 and 2025). This allows underwriters to proactively tighten or loosen credit policy guidelines ahead of market shifts.

### 📊 Core Features & UI Layout

The production-ready dashboard is structured to support rapid executive-level scanning via a balanced grid layout: 

* **Executive KPI Metric Block:** High-impact metric card rendering the **Total Credit** volume figure globally.
* **Asset Allocation Heatmap (Top Right):** A horizontal ranking chart evaluating relative credit weights across sectors, applying a high-contrast color gradient to highlight dominant risk categories.
* **Macro Credit Trends & YoY% Growth (Bottom Left):** An advanced **Dual-Axis Combination Chart** plotting absolute credit volumes against a calculated percentage trajectory line.
* **Financial Performance Matrix (Top Left):** A granular, multi-dimensional tabular text grid delivering exact historical valuations across reporting intervals.

### 🛠️ Tech Stack & Data Engineering Workflow

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




## 📷 Dashboard Preview

![RBI Sectoral Credit Dashboard Preview](<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/28756dac-0e12-4f35-802e-f5c568167128" />
)

