# MIT805
Module related work
# MIT805 — NYC FHV Trip Data Analysis (Jan–Jul 2025)

This repository contains combined high-volume For-Hire Vehicle (FHV) trip data for New York City for the months January through July 2025, along with scripts and analyses exploring the 7 Vs of Big Data.

---

Dataset

- Source: NYC Taxi & Limousine Commission (TLC) Trip Record Data (FHVHV)  - https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page
- Original Format: Parquet  
- Combined Format: CSV  
- Date Range:01 January 2025 - 31 July 2025
- Files Covered: fhvhv_tripdata_2025-01 - fhvhv_tripdata_2025-07
- Total Size of Combined CSV: ~21.9 GB  
- Number of Records: 19,653,012
- Number of Columns: 25
  ['hvfhs_license_num', 'dispatching_base_num', 'originating_base_num', 'request_datetime', 'on_scene_datetime', 'pickup_datetime', 'dropoff_datetime', 'PULocationID', 'DOLocationID', 'trip_miles', 'trip_time', 'base_passenger_fare', 'tolls', 'bcf', 'sales_tax', 'congestion_surcharge',
'airport_fee', 'tips', 'driver_pay', 'shared_request_flag', 'shared_match_flag', 'access_a_ride_flag', 'wav_request_flag', 'wav_match_flag', 'cbd_congestion_fee']

---

## 📈 What Is Analyzed / What You’ll Get

This project includes:

- Scripts / notebooks to merge monthly CSVs into one large dataset  
- Explorations of the 7 Vs of Big Data:
  1. Volume  
  2. Velocity  
  3. Variety  
  4. Veracity  
  5. Variability  
  6. Value  
  7. Visualization  

- Visualizations showing trends such as trips per day, trips by hour, busiest pickup zones, etc.

---

## 💻 How To Use

### Prerequisites

- Python 3.x  
- Required libraries (can install via pip):
  ```bash
  pip install pandas matplotlib seaborn
