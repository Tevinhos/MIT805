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

---

# We will analyze the 7 V's below

This project includes:

- Scripts / notebooks to merge monthly CSVs into one large dataset  
- Explorations of the 7 Vs of Big Data:
  1. Volume
     - Number of records: 19,653,012
       Number of columns: 25
         ['hvfhs_license_num', 'dispatching_base_num', 'originating_base_num', 'request_datetime', 'on_scene_datetime', 'pickup_datetime', 'dropoff_datetime', 'PULocationID', 'DOLocationID', 'trip_miles', 'trip_time', 'base_passenger_fare', 'tolls', 'bcf', 'sales_tax', 'congestion_surcharge',
'airport_fee', 'tips', 'driver_pay', 'shared_request_flag', 'shared_match_flag', 'access_a_ride_flag', 'wav_request_flag', 'wav_match_flag', 'cbd_congestion_fee']

  2. Velocity
       Dates        Trips per day    
     - 2025-07-01    601454
       2025-07-02    583446
       2025-07-03    628058
       2025-07-04    573009
       2025-07-05    613011
       <img width="632" height="389" alt="image" src="https://github.com/user-attachments/assets/c63bdca9-476d-448f-b2ac-aac98ac5e280" />
       Name: pickup_datetime, dtype: int64
       
  3. Variety
     -  hvfhs_license_num               object
        dispatching_base_num            object
        originating_base_num            object
        request_datetime        datetime64[ns]
        on_scene_datetime       datetime64[ns]
        pickup_datetime         datetime64[ns]
        dropoff_datetime        datetime64[ns]
        PULocationID                     int32
        DOLocationID                     int32
        trip_miles                     float64
        trip_time                        int64
        base_passenger_fare            float64
        tolls                          float64
        bcf                            float64
        sales_tax                      float64
        congestion_surcharge           float64
        airport_fee                    float64
        tips                           float64
        driver_pay                     float64
        shared_request_flag             object
        shared_match_flag               object
        access_a_ride_flag              object
        wav_request_flag                object
        wav_match_flag                  object
        cbd_congestion_fee             float64
        dtype: object
        float64           10
        object             8
        datetime64[ns]     4
        int32              2
        int64              1
        dtype: int64
        
  4. Veracity
     - hvfhs_license_num             0
        dispatching_base_num          0
        originating_base_num    5492276
        request_datetime              0
        on_scene_datetime             0
        pickup_datetime               0
        dropoff_datetime              0
        PULocationID                  0
        DOLocationID                  0
        trip_miles                    0
        trip_time                     0
        base_passenger_fare           0
        tolls                         0
        bcf                           0
        sales_tax                     0
        congestion_surcharge          0
        airport_fee                   0
        tips                          0
        driver_pay                    0
        shared_request_flag           0
        shared_match_flag             0
        access_a_ride_flag            0
        wav_request_flag              0
        wav_match_flag                0
        cbd_congestion_fee            0
        dtype: int64
        count    1.965301e+07
        mean     5.110925e+00
        std      6.017682e+00
        min      0.000000e+00
        25%      1.573000e+00
        50%      3.061000e+00
        75%      6.430000e+00
        max      4.505900e+02
        Name: trip_miles, dtype: float64
                 hvfhs_license_num dispatching_base_num originating_base_num  \
        10556               HV0003               B03404               B03404   
        17484               HV0005               B03406                 None   
        20559               HV0003               B03404               B03404   
        32472               HV0003               B03404               B03404   
        47046               HV0003               B03404               B03404   
        ...                    ...                  ...                  ...   
        19632936            HV0003               B03404               B03404   
        19645873            HV0003               B03404               B03404   
        19648626            HV0003               B03404               B03404   
        19649168            HV0003               B03404               B03404   
        19651783            HV0003               B03404               B03404   
        
                    request_datetime   on_scene_datetime     pickup_datetime  \
        10556    2025-07-01 00:02:09 2025-07-01 00:03:22 2025-07-01 00:04:59   
        17484    2025-07-01 01:05:04 2025-07-01 01:08:25 2025-07-01 01:09:25   
        20559    2025-07-01 01:24:03 2025-07-01 01:25:26 2025-07-01 01:25:26   
        32472    2025-07-01 02:02:18 2025-07-01 02:03:04 2025-07-01 02:03:04   
        47046    2025-07-01 05:50:00 2025-07-01 05:34:03 2025-07-01 05:34:08   
        ...                      ...                 ...                 ...   
        19632936 2025-07-31 23:05:00 2025-07-31 23:06:16 2025-07-31 23:08:16   
        19645873 2025-07-31 23:17:45 2025-07-31 23:19:31 2025-07-31 23:20:00   
        19648626 2025-07-31 23:00:24 2025-07-31 23:01:02 2025-07-31 23:01:02   
        19649168 2025-07-31 22:44:02 2025-07-31 23:11:38 2025-07-31 23:11:38   
        19651783 2025-07-31 23:12:12 2025-07-31 23:13:28 2025-07-31 23:13:28   
        
                    dropoff_datetime  PULocationID  DOLocationID  trip_miles  ...  \
        10556    2025-07-01 00:07:05           113           113         0.0  ...   
        17484    2025-07-01 02:29:41           234           234         0.0  ...   
        20559    2025-07-01 01:26:18            70            70         0.0  ...   
        32472    2025-07-01 02:03:57           238           238         0.0  ...   
        47046    2025-07-01 05:34:15           216           216         0.0  ...   
        ...                      ...           ...           ...         ...  ...   
        19632936 2025-07-31 23:12:08           211           211         0.0  ...   
        19645873 2025-07-31 23:24:50            17            17         0.0  ...   
        19648626 2025-07-31 23:04:06           249           249         0.0  ...   
        19649168 2025-07-31 23:19:41           261            88         0.0  ...   
        19651783 2025-07-31 23:16:29           129           129         0.0  ...   
        
                  congestion_surcharge  airport_fee  tips  driver_pay  \
        10556                     2.75          0.0   0.0        4.00   
        17484                     2.75          0.0   0.0       81.57   
        20559                     0.00          0.0   0.0        4.00   
        32472                     2.75          0.0   0.0        8.04   
        47046                     0.00          0.0   0.0        4.00   
        ...                        ...          ...   ...         ...   
        19632936                  0.00          0.0   0.0        0.00   
        19645873                  0.00          0.0   0.0        0.68   
        19648626                  2.75          0.0   0.0        0.00   
        19649168                  0.75          0.0   0.0        0.00   
        19651783                  0.00          0.0  12.2        0.00   
        
                  shared_request_flag  shared_match_flag  access_a_ride_flag  \
        10556                       N                  N                   N   
        17484                       N                  N                   N   
        20559                       N                  N                   N   
        32472                       N                  N                   N   
        47046                       N                  N                   N   
        ...                       ...                ...                 ...   
        19632936                    N                  N                   N   
        19645873                    N                  N                   N   
        19648626                    N                  N                   N   
        19649168                    Y                  N                   N   
        19651783                    N                  N                   N   
        
                  wav_request_flag  wav_match_flag cbd_congestion_fee  
        10556                    N               N                1.5  
        17484                    N               N                1.5  
        20559                    N               N                0.0  
        32472                    N               N                0.0  
        47046                    N               N                0.0  
        ...                    ...             ...                ...  
        19632936                 N               N                0.0  
        19645873                 N               Y                0.0  
        19648626                 N               N                0.0  
        19649168                 N               N                0.0  
        19651783                 N               N                0.0  
        
        [2155 rows x 25 columns]
        Duplicates: 0

  5. Variability  
  6. Value
   -              pickup_datetime  trip_miles
        9253447  2025-07-16 03:56:42      450.59
        8709765  2025-07-15 07:11:37      374.96
        3018289  2025-07-06 00:16:32      299.50
        713220   2025-07-02 08:12:41      287.16
        19242312 2025-07-31 12:44:32      286.17

        <img width="512" height="431" alt="image" src="https://github.com/user-attachments/assets/950d08ae-4767-42fe-aa92-c55797bb9214" />
      

  12. Visualization  

- Visualizations showing trends such as trips per day, trips by hour, busiest pickup zones, etc.

---

## 💻 How To Use

### Prerequisites

- Python 3.x  
- Required libraries (can install via pip):
  ```bash
  pip install pandas matplotlib seaborn
