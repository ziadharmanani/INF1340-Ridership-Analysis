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

## Models Implemented  
- **Naive Bayes** — baseline classifier for trip-duration categories  
- **Logistic Regression (Logit)** — peak-hour classification using temporal & duration features  
- **Random Forest Classifier** — flexible, nonlinear model trained on engineered features  

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
