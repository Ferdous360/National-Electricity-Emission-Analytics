# Australian Grid Emission Intensity: Intra-Daily Analysis (2019-2025)

## 📌 Project Overview
This project implements a high-performance data engineering pipeline to analyze fluctuations in electricity grid emission intensity across the Australian National Electricity Market (NEM). By integrating high-resolution API data with modern processing tools, the analysis quantifies the "Carbon Premium" of peak-hour energy use and identifies optimal "Green Windows" for strategic load-shifting.

## 📊 Key Insights
* **Temporal Volatility:** Demonstrated that grid carbon intensity varies by over 50% within a 24-hour cycle due to shifting renewable penetration.
* **Peak vs. Off-Peak Impact:** Households often have a lower total carbon footprint than commercial entities—even with similar energy volumes—because their consumption aligns with cleaner off-peak hours.
* **Regional Benchmarking:** Comparative analysis of NSW, QLD, VIC, SA, and TAS grids, tracking the transition from fossil-fuel reliance to renewable integration.

## 🛠️ Technical Stack
* **Data Engineering:** `Polars` (High-performance multi-threaded dataframes), `Parquet` (Columnar storage).
* **API Integration:** `Requests-OAuth2Client` for secure CSIRO Senaps API authentication.
* **Visualization:** `Matplotlib` & `Seaborn` for time-series decomposition and hourly trend mapping.
* **Environment:** Python 3.11+

## 📂 Data Pipeline Architecture
1. **Extraction:** Custom `MyEmissionsData` class handles OAuth2 handshakes and automated JSON retrieval from CSIRO Senaps.
2. **Transformation:** Sub-second processing of 5-minute interval data using Polars for memory efficiency and speed.
3. **Storage:** Raw data is converted into optimized Parquet files, maintaining schema integrity and reducing disk usage.
4. **Analysis:** Feature engineering extracts cyclical time components (Hour, Month, Year) to isolate intra-daily patterns.



## 🚀 Getting Started
### Prerequisites
```bash
pip install polars requests_oauth2client matplotlib seaborn
