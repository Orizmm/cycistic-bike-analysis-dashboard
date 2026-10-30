import pypandoc, os

markdown = r"""# Cyclistic Bike-Share Analysis
### Understanding How Annual Members and Casual Riders Use Cyclistic Differently

![Python](https://img.shields.io/badge/Python-EDA-blue?logo=python)
![Tableau](https://img.shields.io/badge/Tableau-Data%20Visualization-E97627?logo=tableau)
![Status](https://img.shields.io/badge/Project-Completed-success)

## Project Overview

This project analyzes Cyclistic's bike-share trip data to understand how **annual members** and **casual riders** use the service differently.

Cyclistic is a fictional bike-share company operating in Chicago. Its marketing team wants to increase the number of annual memberships. To support that goal, this analysis explores differences in riding patterns and identifies opportunities to encourage casual riders to become annual members.

The analysis focuses on the first business question in the case study:

> **How do annual members and casual riders use Cyclistic bikes differently?**

## Business Objective

The main objective is to compare member and casual rider behavior and translate the findings into practical marketing recommendations.

The analysis explores:

- Ride volume by customer type.
- Usage patterns across days of the week and hours of the day.
- Average ride duration.
- Preferred bike types.
- The most frequently used start and end stations.

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Python | Data cleaning, preparation, and exploratory data analysis (EDA) |
| Pandas & NumPy | Data manipulation and calculations |
| Matplotlib | Exploratory charts and data checks |
| Tableau | Interactive data visualization and dashboard development |

## Dataset

The dataset contains individual bike trips and includes fields such as:

- `ride_id` — unique ride identifier
- `rideable_type` — type of bicycle used
- `started_at` and `ended_at` — trip start and end timestamps
- `start_station_name` and `end_station_name` — trip origin and destination
- `start_lat`, `start_lng`, `end_lat`, and `end_lng` — station coordinates
- `member_casual` — rider category (`member` or `casual`)
- `hour_of_day`, `day_of_week`, and `month` — time-related attributes
- `ride_length_min` — trip duration in minutes

The dashboard presented in this project covers **2025** and reports **3,661,552 rides**.

> **Data note:** The analysis uses trip-level records. The available fields do not identify individual customers, explain their trip purpose, or show whether a particular casual rider later became a member. Therefore, ride counts should not be interpreted as unique customer counts, and customer motivations cannot be confirmed from this dataset alone.

## Analysis Process

The project follows the data analysis process: **Ask, Prepare, Process, Analyze, Share, and Act.**

### 1. Ask — Define the Business Task

Compare how annual members and casual riders use Cyclistic bikes. The findings should help the marketing team identify relevant opportunities to convert casual riders into annual members.

### 2. Prepare — Understand the Data

Review the trip dataset, its structure, available fields, date coverage, and limitations. The data is used to examine ride behavior while respecting the privacy restrictions described in the case study.

### 3. Process — Clean and Prepare

The preparation stage includes:

- Checking data types and converting timestamp fields to datetime.
- Reviewing missing values and duplicate ride records.
- Validating trip duration.
- Creating or checking time-based features such as month, day of week, and hour.
- Reviewing station names and geographic coordinates before location analysis.

Cleaning decisions should be documented, especially when handling missing station information and unusual trip durations.

### 4. Analyze — Explore Riding Patterns

The EDA compares members and casual riders across several dimensions:

- Total rides and ride share.
- Monthly and weekly ride trends.
- Ride volume by hour of day.
- Average ride duration.
- Bike-type usage.
- Popular start and end stations.

### 5. Share — Build the Tableau Dashboard

The Tableau dashboard presents the findings through KPI summaries, trend charts, duration comparisons, bike-type comparisons, and station rankings.

### 6. Act — Develop Recommendations

The findings are translated into marketing opportunities and suggestions for further testing.

## Key Findings

Based on the 2025 dashboard:

### 1. Members Account for the Larger Share of Rides

- Total rides: **3,661,552**
- Annual member rides: **2,351,436 (64.2%)**
- Casual rides: **1,310,116 (35.8%)**

Annual members account for most recorded trips. However, casual riders still contribute more than one-third of total ride volume and represent a relevant audience for membership campaigns.

### 2. Usage Patterns Differ by Day of the Week

Member ride volume is relatively strong throughout the workweek, while casual ride volume increases toward the weekend and reaches its highest point on Saturday.

This pattern may indicate different usage needs. It is consistent with the possibility that members use the service more regularly, while casual riders are more active during weekend periods. Trip purpose cannot be confirmed from the available data.

### 3. Casual Riders Generally Take Longer Trips

The dashboard shows that casual riders have a higher average ride duration than annual members across the hours displayed. At one point, casual average ride duration reaches approximately **27.56 minutes**, while member duration remains around **11–14 minutes**.

This difference suggests that the two groups may use the service in different ways. Further research would be needed to understand the reasons behind these longer trips.

### 4. Classic Bikes Have the Highest Ride Volume

Classic bikes record the highest number of rides for both customer groups.

| Bike Type | Member Rides | Casual Rides |
|---|---:|---:|
| Classic Bike | 1,274,437 | 667,942 |
| Electric Bike | 1,076,999 | 642,174 |

The split between classic and electric bike usage is more balanced among casual riders than among members.

### 5. Station Usage Varies by Customer Type

Some popular stations, including DuSable Lake Shore Dr & Monroe St and Navy Pier, show substantial casual ride volume. Kingsbury St & Kinzie St has a stronger member presence in the displayed station rankings.

These differences suggest that station-level usage can help identify locations for targeted marketing. Station labels and possible duplicate or truncated names should be checked before final interpretation.

## Tableau Dashboard

The dashboard includes the following views:

1. **Member vs. Casual Ride Share** — compares total ride volume by rider category.
2. **Ride Trend by Day of the Week** — compares weekly usage patterns.
3. **Ride Trend by Hour of the Day** — identifies daily peak usage periods.
4. **Average Ride Duration by Hour** — compares trip duration patterns.
5. **Bike Type** — compares classic and electric bike usage.
6. **Top 10 Start Stations** — highlights the most frequently used trip origins.
7. **Top 10 End Stations** — highlights the most frequently used trip destinations.

### Dashboard Preview

Add your Tableau dashboard screenshot to the repository and update the image path below:

```markdown
![Cyclistic Tableau Dashboard](images/cyclistic_dashboard.png)
```

**Live Dashboard:** https://public.tableau.com/views/cyclistic_17933710455460/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

## Business Recommendations

### 1. Test Weekend Membership Campaigns

Casual ride volume is highest on Saturday. Test campaigns before and during weekends that communicate the convenience and potential value of an annual membership to riders who use Cyclistic regularly.

### 2. Use Location-Based Marketing

Identify stations with both high casual ride volume and a high casual share. Consider these locations for targeted promotions, then measure whether the campaigns generate additional memberships.
