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

### 1. Data Cleaning & Transformation (Power Query)

* Sourced raw central bank financial spreadsheets.
* Cleaned headers, adjusted data formats, handled missing records, and optimized data density within the **Power Query Editor**.

### 2. Semantic Data Modeling (Star Schema)

* Abandoned cluttered flat files to construct a relational **Star Schema** data structure to ensure high query performance.
* Linked isolated attribute dimensional tables (rbi_analytics_view_dim_time and rbi_analytics_view_dim_metric_sector) to a central transactional fact table utilizing precise primary/foreign key mappings.

### 3. Business Logic & Interactivity (Tableau)

* Developed responsive **Action Filters** across components, enabling stakeholders to dynamically slice the entire canvas simply by interacting directly with the asset allocation layers.
* Applied advanced table calculations to isolate and evaluate relative market dynamics independent of raw currency weights.

*Developed as part of an advanced financial analytics portfolio project for corporate risk and credit review evaluation.*
