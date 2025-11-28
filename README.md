# INF1340: Bike Share Toronto Ridership Analysis

Karen Eng, Ziad Harmanani, Mara Silver

Instructor: Dr. Maher Elshankankiri 

Course code: INF1340
Course name: Programming for Data Science
Program: Master of Information
Faculty of Information
University of Toronto

Date Created: 2025-11-13

## Introduction

## Project Overview
This project analyzes the Bike Share Toronto ridership dataset for 2023, focusing on key usage patterns and predictive modeling. The goal is to understand how temporal trip characteristics relate to trip duration and peak hour usage.

| Variable                   | Description                                      |
| -------------------------- | ------------------------------------------------ |
| `Trip Duration`            | Length of trip in seconds (converted to minutes) |
| `Start Time`               | Timestamp of trip start                          |
| `Start Month`, `Start Day` | Extracted from start timestamp                   |
| `End Time`                 | Timestamp of trip end                            |
| `Start Month`, `Start Day` | Extracted from start timestamp                   |
| `Weekday/Weekend (Binary)` | 1 = weekday, 0 = weekend                         |
| `Peak Hour (Binary)`       | 1 = 7 - 9am or 4 - 6pm                           |
| `Log_Trip_Duration`        | Natural log of trip duration                     |
| `Trip_Duration_Category`   | Very Short / Short / Medium / Long / Very Long   |


## Dataset Description
This project uses the Bike Share Toronto Ridership Data, available through the City of Toronto’s Open Data Portal. The data is organized by year, with each year containing 12 monthly CSV files. Each monthly file typically contains over 100,000 rows, where each row represents a single trip taken using the Tangerine Bike Share system.

**Data Source:** City of Toronto. Bike Share Toronto Ridership Data.  
Available at: https://open.toronto.ca/dataset/bike-share-toronto-ridership-data/
