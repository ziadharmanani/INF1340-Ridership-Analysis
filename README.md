# INF1340: Bike Share Toronto Ridership Analysis

Karen Eng, Ziad Harmanani, Mara Silver

Instructor: Dr. Maher Elshankankiri 

Course code: INF1340
Course name: Programming for Data Science
Program: Master of Information
Faculty of Information
University of Toronto

Date Created: 2025-11-13

# Bike Share Toronto 2023 Ridership Analysis

## Project Overview  
This project analyzes the 2023 Bike Share Toronto dataset to explore ridership patterns and build predictive models for trip duration and peak-hour usage.  

## Dataset Description  
The dataset comprises 12 monthly CSV files (Jan–Dec 2023), each containing ~100,000–500,000 records. 
Available at: https://open.toronto.ca/dataset/bike-share-toronto-ridership-data/
Key raw fields include: Trip Duration, Start/End Station (ID & name), Start/End time stamps, User Type, and Trip ID.  
Several derived variables were engineered to support analysis: start-day/month/hour, weekday/weekend flag, peak-hour categories, log-duration, and trip-duration categories (Very Short → Very Long).  

## Data Cleaning & Preprocessing  
- Merged all monthly CSVs into a single dataframe  
- Cleaned inconsistent column names (BOM removal, whitespace)  
- Parsed date/time, extracted new temporal variables (day, month, hour)  
- Created binary weekday/weekend and peak-hour labels  
- Filtered out invalid or extreme trips (e.g. duration <1 min or > 99th percentile)  
- Converted duration to human-readable and log-scaled formats

## Variables

| Variable Name               | Description                                        |
|-----------------------------|----------------------------------------------------|
| End Date                    | Extracted end date from End Time                  |
| End Day                     | Day extracted from End Time                       |
| End Month                   | Month extracted from End Time                     |
| End Station Id              | ID of the ending station                          |
| End Station Name            | Name of the ending station                        |
| End Time                    | Timestamp of trip end (YYYY-MM-DD)                |
| Peak Hour                   | Indicator of whether start time is in peak hours  |
| Peak Hour (Binary)          | Binary peak-hour indicator (1 = Peak, 0 = Off Peak) |
| Start Date                  | Extracted start date from Start Time              |
| Start Day                   | Day extracted from Start Time                     |
| Start Hour                  | Hour extracted from Start Time                    |
| Start Month                 | Month extracted from Start Time                   |
| Start Station Id            | ID of the starting station                        |
| Start Station Name          | Name of the starting station                      |
| Start Time                  | Timestamp of trip start (YYYY-MM-DD)              |
| Trip Duration               | Duration of the trip (seconds)                    |
| Trip_Duration_Category      | Categorical duration label (Very Short, Short, Medium, Long, Very Long) |
| Log_Trip_Duration           | Log-transformed trip duration for normalization   |
| Trip Duration (mm:ss)       | Trip duration converted to mm:ss format           |
| User Type                   | Type of user (Casual or Annual)                   |
| Weekday/Weekend             | Start date classified as weekday or weekend       |
| Weekday/Weekend (Binary)    | Binary weekday indicator (1 = Weekday, 0 = Weekend) |

## Project Structure  
```
INF1340-Ridership/
│── Bike share ridership/  
│   └── Bike share ridership 2023-01
│   └── ...
│   └── Bike share ridership 2023-01
│── rideshare_cleaning.ipynb 
└── README.md    
```

## How to Run the Code  
1. Install dependencies: `pip install -r requirements.txt`  
2. Place raw monthly CSVs into `INF1340-Ridership/Bike share ridership`  
3. Run `ridership_cleaning.ipynb`

## Dependencies  
- Python 3.x  
- pandas, numpy, scikit-learn, statsmodels, matplotlib, seaborn  

## Known Limitations & Future Work  
- No station-level or geospatial data → cannot model route distance or traffic effects  
- Weather data not included, which may influence trip durations  
- Potential bias from missing station IDs/names (~10% of trips)  
- Future: incorporate station coordinates, weather, temporal demand variation  

## Authors
Karen Eng
Ziad Harmanani
Mara Silver
