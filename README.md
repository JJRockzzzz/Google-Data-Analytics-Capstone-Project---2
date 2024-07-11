# Google Case Study 2: Cyclistic Bike Share Case Study
## Quick Links:
### Data Source: [divvy_tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html)

## Introduction

Cyclistic Marketing Analysis

As a junior data analyst on the marketing analyst team at Cyclistic, your objective is to understand how casual riders and annual members use Cyclistic bikes differently. This analysis aims to develop insights that will inform a new marketing strategy to convert casual riders into annual members. To proceed, Cyclistic executives require data-driven recommendations supported by compelling data insights and professional visualizations.

The company seeks to answer the following three key questions for the future marketing program based on the dataset:

How do annual members and casual riders use Cyclistic bikes differently?

Usage Patterns: Analyze the differences in trip duration, frequency, and time of day/week between annual members and casual riders.
Trip Locations: Investigate if there are specific stations or routes that are more popular among annual members compared to casual riders.
Bike Types: Determine if there's a preference for certain types of bikes (standard, electric, etc.) among annual members versus casual riders.
Why would casual riders buy Cyclistic annual memberships?

Cost Savings: Highlight the potential cost savings for frequent riders if they switch to an annual membership.
Convenience: Emphasize the added convenience of an annual membership, such as priority access to bikes and more flexible usage terms.
Incentives: Identify what incentives (e.g., discounts, exclusive access to events) could motivate casual riders to become annual members.
How can Cyclistic use digital media to influence casual riders to become members?

Targeted Campaigns: Use data insights to create targeted digital marketing campaigns aimed at casual riders, emphasizing the benefits of an annual membership.
Engagement Strategies: Develop engagement strategies on social media platforms to build a community and foster a sense of belonging among casual riders.
Personalized Offers: Leverage digital media to deliver personalized offers and promotions to casual riders based on their usage patterns and preferences.

## Tools used in Analysis
- Data Cleaning: Microsoft Excel 
- Data Analysis: Microsft SQL Server 
- Visualization: Tableau Public

## Data Analysis Process
To effectively analyze Cyclistic data and address key business questions while making informed recommendations, the data analysis process will adhere to the following key steps: Ask relevant questions, Prepare the data for analysis, Process the data to ensure accuracy and relevance, Analyze the data to derive meaningful insights, Share findings through clear and actionable reports or presentations, and Act upon the insights to drive strategic decisions and improvements. These steps ensure a structured approach to deriving insights from data for informed business decisions at Bellabeat.

### Ask Phase:

To address the business task of understanding how annual members and casual riders use Cyclistic bikes differently, the following questions will guide the analysis:

1. Percentage of Casual Riders vs Annual Members
2. Proportion of Rides by Bike Type
3. Percentage of Rides per Month
4. Number of Rides per Day
5. Average Ride Duration by Day (in minutes)
6. Frequency of Rides per Hour
7. Percentage of Rides per Season
8. Proportion of Rides in Each Time Zone
### Prepare Phase:
- The dataset used for this project is public data provided by Motivate International Inc. It consists of monthly files covering the period from January 2022 to December 2022. 
- Each file within the dataset contains 13 columns related to the bike rides. 
- These columns provide detailed information about each ride, including the ride ID, rideable type, start and end station ID’s and locations, coordinates, and membership type.

### Process Phase:
#### Cleaning in Excel:

During the process phase, data cleaning steps were carried out in Microsoft Excel. The following actions were performed:

1. Checking for Duplicates: Duplicate values were identified and removed using the built-in “Remove Duplicates” feature in Excel. This helped ensure data integrity and eliminate any duplicated entries.
2. Validating Column Values: The values in specific columns, such as rideable_type and member_casual, were verified for consistency and accuracy. Only valid values, including classic_bike, docked_bike, and electric_bike for rideable_type, and casual, member for member_casual, were retained.
3. Removing Blank Values: The dataset was checked for incomplete or blank values across all columns. Rows with missing values, particularly in columns like start_station_name, start_station_id, end_station_name, and end_station_id, were removed to ensure data completeness.
4. Removing Unwanted Columns: Columns such as start_lat, start_lng, end_lat, and end_lng, which were not relevant to the analysis, were removed from each file to streamline the dataset and focus on essential variables.
5. Adding the Ride Length Column: A new column named “ride_length” was added to calculate the duration of each ride. The value in the ride_length column was obtained by subtracting the started_at timestamp from the ended_at timestamp.
6. Setting the Time Format: The ride_length column was formatted as “HH:MM
” using the “Format > Cells > Time > 37:30:55” option in Excel. This ensured that the ride duration was presented in a standardized time format.
Applying Conditional Formatting: Conditional formatting was applied to the ride_length column to highlight ride lengths that fell outside the desired range. Specifically, any ride length values less than 00:01:00 (one minute) or greater than 24:00:00 (24 hours) were formatted differently, making them easily identifiable for further analysis or potential removal.
7. Sorting the Table: The table was sorted in ascending order based on the started_at column to ensure data consistency.

By cleaning data in Excel, the dataset was refined, inconsistencies were addressed, and the ride length information was formatted appropriately for subsequent analysis.

#### Data Transformation:
For data transformation, data processing was performed in SQL Server. The data from each month, spanning from January to December 2022, was imported and merged into a single table called “Annual_trip_data_2022.” The steps involved in this process are as follows:

Importing Data: The monthly files containing the ride data were imported into SQL Server.
Merging Data: A new table named “Annual_trip_data_2022” was created to store the consolidated data for the entire year. The data from the tables were merged into the “Annual_trip_data_2022” table using the UNION ALL statement. SQL Query: Merge Data [(https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/Merge%20Data.sql)]
Data Manipulation: After merging data, a new table named “analyze_annual_trip_data” was generated. This table includes additional columns such as “month,” “day,” “hour,” and “duration_minutes” to facilitate the comparison and analysis of ride frequencies. SQL Query: Manipulate Data
[(https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/Manipulate%20Data.sql)]

### Analyze Phase:

In the Analyze phase, we delve into the data to uncover insights and address the key findings related to how annual members and casual riders use Cyclistic bikes differently. The focus is on understanding their behavior, preferences, and patterns to inform marketing strategies aimed at converting casual riders into annual members. To address the key findings, the following analyses were performed in SQL Server. 

#### 1. Percentage of Casual Riders vs Annual Members
SQL Query: [Analyze Data](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/Analyze%20Data.sql) 

<img width="316" alt="3  percentage of rides - result" src="https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG1.png">

#### 2. Proportion of Rides by Bike Type 
SQL Query: [Analyze Data](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/Analyze%20Data.sql) 

<img width="446" alt="4  rides by bike types - result" src="https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG2.png">

#### 3. Percentage of Rides per Month
SQL Query: [Analyze Data](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/Analyze%20Data.sql) 

<img width="412" alt="5  rides per month - result" src="https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG3.png">

#### 4. Number of Riders per Day
SQL Query: [Analyze Data](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/Analyze%20Data.sql) 

<img width="213" alt="6  number of rides by day - result" src="https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG4.png">

#### 5. Average Ride Duration by Day (in minute)
SQL Query: [Analyze Data](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/Analyze%20Data.sql) 

<img width="208" alt="7  average ride duration by days - result" src="https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG5.png">

#### 6. Frequency of Rides per Hour
SQL Query: [Analyze Data](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/Analyze%20Data.sql) 

![number of rides per hour](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG6.png)

#### 7. Percentage of Rides per Season 
SQL Query: [Analyze Data](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/Analyze%20Data.sql) 

<img width="425" alt="9  rides by season - result" src="https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG7.png">

#### 8. Percentage of Rides per Time Zone 
SQL Query: [Analyze Data](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/Analyze%20Data.sql) 

<img width="421" alt="10  percentage of rides by time zone - result" src="https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG8.png">

### Share Phase: 

The share phase presents the insights and findings derived from the analysis of Cyclistic Bike Share data using Tableau Public, a powerful data visualization tool. The analysis revealed several key findings:

#### 1. Percentage of Casual Riders vs Annual Members
In 2022, annual members accounted for the majority of the rides, representing 59.35% of the total 4,288,562 rides.
![sheet1](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG11.png)

#### 2. Proportion of Rides by Bike Type

The analysis of bike types reveals that annual members have a higher percentage of using classic bikes compared to casual riders. Additionally, annual members show a greater preference for electric bikes compared to casual riders. However, when it comes to docked bikes, casual riders demonstrate a higher inclination towards using them compared to annual members.
![sheet2](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG12.png)

#### 3. Percentage of Rides per Month
This analysis reveals that annual members consistently have a higher number of rides compared to casual riders in all months. In February, annual members accounted for the highest proportion of rides, reaching approximately 82.93%. On the other hand, casual riders had the highest proportion of rides in July, comprising nearly 48.59% of the total rides.
![sheeet 3](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG13.png)

#### 4. Number of Rides per Day 
The analysis of the number of rides per day reveals interesting patterns. From Monday to Friday, annual members consistently have a higher count of rides compared to casual riders. However, on weekends (Saturday and Sunday), casual riders exhibit the highest usage, surpassing the number of rides by annual members.
![sheet4](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG14.png)

#### 5. Average Ride Duration by Day (in minutes)
On average, casual riders have significantly longer ride durations compared to annual members.
![sheeet5](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG15.png)

#### 6. Frequency of Rides per Hour
The line graph illustrates distinct variations in the frequency of rides per hour for both annual members and casual riders. Notably, both rider type experience peak usage at 17:00 (5 p.m.), with annual members recording 273,000 rides and casual riders with 167,000 rides during that hour.
![sheet6](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG16.png)

#### 7. Percentage of Rides per Season
Overall, annual members consistently have the highest proportion of rides in all seasons compared to casual riders. However, during winters, annual members have the highest proportion, accounting for approximately 78.99% of the total rides. On the other hand, casual riders have the highest proportion of rides during summers, comprising around 46.86% of the total rides.
![sheet7](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG17.png)

#### 8. Proportion of Rides in each Time Zone
Annual Members have the highest ratio of bike usage across the three time zones: morning, afternoon, and evening. Specifically, in the morning time zone, annual members account for approximately 68.15% of the rides, indicating their dominant presence during that period. However, casual rides surpass members in the night time zone, comprising about 50.57% of the rides.
![sheet8](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project---2/blob/main/IMG18.png)

### Act Phase 
### Key Takeaways 
Based on the findings of my analysis, several key takeaways can be derived:

1) Bike Type Preference: Annual members show a higher preference for classic and electric bikes, while casual riders are more inclined toward docked bikes.
2) Monthly Variation: Annual members consistently have more rides than casual riders each month. February sees the highest proportion of annual members' rides, while July has the highest proportion of casual rides.
3) Weekday vs. Weekend Usage: Annual members tend to ride more on weekdays, whereas casual riders have higher usage on weekends.
4)Ride Duration: Casual riders have longer average ride durations compared to annual members.
5) Peak Usage Hour: Both annual members and casual riders experience peak usage at 5 p.m., with annual members having a higher number of rides.
6) Seasonal Variation: Members have the highest proportion of rides in all seasons, but winters see the highest proportion of annual members' rides, while summers see the highest proportion of casual rides.
7) Time Zone Distribution: Annual members dominate the morning, afternoon, and evening time zones, while casual riders have a higher proportion of rides during the night.

### Recommended Strategies
1) Targeted Promotions: Offer exclusive discounts or incentives for casual riders to upgrade to annual memberships, emphasizing the benefits and cost savings of long-term commitment.
2) Improved Bike Variety: Expand the fleet of classic and electric bikes to cater to the preferences of casual riders and enhance their overall riding experience.
3) Customized Membership Plans: Introduce tailored annual membership plans specifically for docked bike users, providing additional perks and advantages to encourage their transition.
By implementing these strategies, Cyclistic can enhance user experience, increase annual memberships, and better meet the diverse needs of its riders.

 


## Visualization 

![dashboard](https://github.com/JJRockzzzz/Google-Data-Analytics-Capstone-Project-2/tree/main)
