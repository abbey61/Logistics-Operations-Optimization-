## Executive Summary
This repository contains the end-to-end Data Analytics Capstone Project completed for my **TS Academy Certification**.

My role was to act as the lead Data Analyst, responsible for cleaning, modeling, and visualizing the data to uncover trends and provide recommendations. 
This project allowed me to apply end-to-end analytics skills — from data preparation to dashboard design, using Power BI as the primary tool.

The project utilizes a complex logistics operations dataset (85K+ rows) to isolate critical business bottlenecks, evaluate costly supply chain leakages, and recommend data-backed operational frameworks. 

While the logistics engine demonstrates phenomenal fundamental health—boasting a **65% Gross Profit Margin**—deep-seated inefficiencies are choking maximum throughput. 
The operation is heavily bound by a poor **On-Time Delivery (OTD) rate of 56%**, extensive vehicle idling (**598.79K total idle hours**), 
and a steep gap in revenue capture, realizing **$298.62M** out of a theoretical maximum potential revenue of **$538M** (leaving **44.5% of revenue unfulfilled**).

---
# Business Challenges:
The Logistics Company was data-rich but poor insight. Management lacked clarity on key performance drivers and needed answers to critical questions:

- Which routes are generating most revenues and the cost by lane?

- Which driver is costing the company most money due to delivery time and safety metrics?

- Which customer is generating most revenue?

- How can operational inefficiencies be identified and addressed?

The challenge was to transform raw, fragmented data into structured insights that could guide executive decision-making and improve overall business performance.

# Data Overview & Preparation
**Datasets Used:**

- **Drivers:** Driver demographics, employment history, license info

- **Customers:** Customer accounts, contract types, revenue potential

- **Trucks:** Fleet equipment details, acquisition info, status

- **Trailers:** Trailer inventory, types, status

- **Facilities:**  Terminal and warehouse locations, capacity

- **Routes:** Origin-destination pairs, distances, rate structures

- **Loads:** Shipment details, revenue, booking type

- **Trips:** Actual trip performance, fuel consumption, duration

- **Fuel Purchases:** Fuel transactions, prices, locations

- **Maintenance Records:** Service history, costs, downtime

- **Delivery Events:** Pickup/delivery timestamps, detention, on-time status

- **Safety Incidents:** Accidents, violations, damage costs

- **Driver Monthly Metrics(Aggregated):** Monthly performance summaries per driver

- **Truck Utilization Metrics(Aggregated):** Monthly equipment utilization summaries

# Preparation Steps:

- Removed duplicates and standardized formats

- Validated data types and segmented numerical values

- Created calculated columns (e.g., Delivery Time)

- Built a clean, structured dataset ready for modeling and visualization

# Data Modeling & DAX Measures
I designed a star schema with a central Fact Table (Trips, Load, and Delivery Events) and supporting Dimension Tables (Customers, Trailers, Truck, Drivers, Routes, Fuel Purchases, Maintenance Records, Driver Monthly Metrics(Aggregated), Truck Utilization Metrics(Aggregated), Safety Incidents). 
Relationships enabled seamless filtering and cross-analysis across dashboards.

## Key DAX Measures:

- **Anchor Metrics:** Total Revenue, Operating Cost, Avg Order Value, Conversion Rate, Total Miles, Fleet Trip MPG, Avg Maintenance Downtime Hours, Avg Fuel Cost  

---
## Key Operational Metrics (KPIs)
* **Realized Revenue:** $298.62M | **Potential Capacity Revenue:** $538M
* **Fleet Profitability:** 65% Gross Margin
* **Service Level Agreements (SLA):** 56% On-Time Delivery Rate (44% Delayed)
* **Asset Friction:** 598.79K Non-Productive Idle Hours
* **Driver Retention Metrics:** 17.3% Driver Turnover Rate (26 of 150 Terminated)

---

## Deep-Dive Section Insights

### 1. Financial & Safety Performance
* **Safety Spending Seasonality:** Total safety claims show high volatility throughout the fiscal cycle, spiking heavily in **May ($379K)** and **October ($318K)**, while bottoming out in **December ($106K)**. 
* **High-Risk Operators:** Risk profiling identified specific drivers who generate substantial revenue but incur heavy liability costs. For example, driver **Richard Garcia** generated $2.56M in revenue but accumulated a massive **$50,128 in safety claims cost**, flagging a critical need for targeted coaching.

![My image description](https://github.com/abbey61/Logistics-Operations-Optimization-/blob/main/Logistics%20Financial%26Safety%20Dashboard.png)

### 2. Fleet & Asset Optimization
* **The Idling Drain:** The fleet accumulated **598.79K idle hours**, stagnating the collective trip fuel efficiency to an average of **6.45 MPG**.
* **Maintenance Sinkholes:** The baseline network maintenance downtime is **24.74 hours per vehicle**. However, extreme mechanical outliers like `TRK001080` (**1,080 hours**) and `TRK000996` (**996 hours**) are severely reducing fleet availability.
* **Claims Segmentation:** **Equipment Damage ($741K)** and **DOT Violations ($581K)** lead the organization's incident liability metrics.

![Image Description](https://github.com/abbey61/Logistics-Operations-Optimization-/blob/main/Logistics%20Fleet%26Asset%20Dashboard.png)

### 3. Route & Facility Bottlenecks
* **Detention Time Violations:** Long loading dock delays are the primary driver of late arrivals. The network average detention time stands at **92 minutes**. 
* **Worst Performing Hubs:** The **Indianapolis Warehouse Hub** leads the network in driver friction with a staggering **106-minute average detention time**, followed by the **Phoenix Distribution Center (93.02 mins)**.
* **Fixed Facility Costs:** Regional supply hubs (Kansas, Houston, Columbus) exhibit an identical, invariant maintenance overhead of **$4.3M per hub**, heavily outstripping safety costs.

![Image Description](https://github.com/abbey61/Logistics-Operations-Optimization-/blob/main/Logistics%20Route%20Efficiency%20Dashboard.png)
![Image Description](https://github.com/abbey61/Logistics-Operations-Optimization-/blob/main/Logistics%20Delivery%20Performance%20Dashboard.png)

### 4. Customer Vertical Vulnerabilities
* **Churn and Inactivity Risks:** While the active portfolios in **Automotive ($47M)** and **Food/Beverages ($42M)** remain stable, the **Retail vertical holds $12M in "Inactive" account status**, representing a massive churn leak that requires urgent sales intervention.

![Image Description](https://github.com/abbey61/Logistics-Operations-Optimization-/blob/main/Logistics%20Customer%20Dashboard.png)

---

## Strategic Optimization Framework (Data-Driven Recommendations)

1.  **Idle Reduction Protocols:** Implement automatic 5-minute engine-shutdown limits and equip long-haul trucks with Auxiliary Power Units (APUs) to clear out the **598.79K idle hours** and protect fuel margins.
2.  **Enforce Warehouse Demurrage Fees:** Introduce contract clauses imposing standard detention fines ($75/hour) after 60 minutes for high-delay facilities in **Indianapolis and Phoenix** to improve the low **56% On-Time Delivery rate**.
3.  **Predictive Asset Renewal:** Retire or completely overhaul chronic breakdown trucks (like `TRK001080`) and shift the **$4.3M localized hub budgets** from a fixed model to a predictive framework targeting **Equipment Damage ($741K)**.
4.  **Sales Win-Back Campaigns:** Deploy account executives to target the **$12M inactive retail** and **$8M inactive automotive** accounts to narrow the $239.38M revenue capture gap.
