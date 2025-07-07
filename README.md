# Smart-City-Traffic-Plans
This project uses time series forecasting to predict traffic patterns across four key junctions in a smart city. It helps government planners to anticipate traffic peaks, optimize infrastructure and manage congestion effectively.
This project was developed with the government initiative for Smart City infrastructure with the goal to forecast traffic patterns across four key city junctions to assist in traffic management, peak planning and infrastructure design.

## Project Overview
As the cities evolve into smart ecosystems, traffic congestion remains a major challenge. 
This project builds an intelligent forecasting system using time series and helps to:
- Predict traffic flow across **four junctions**
- Understand daily, weekly, and seasonal traffic patterns
- Account for traffic anomalies during **holidays and city events**
- Assist city planners with **future infrastructure strategies**

## Dataset
The dataset provided consists of two parts:
  File Name            | Description                                        
 `train_aWnotuB.csv`   | Historical traffic data with timestamps, junction ID, and vehicle counts 
 `test_BdBKkAj.csv`    | Future timestamps for which traffic needs to be forecasted 

Each data point includes:
- `DateTime` – Timestamp of observation
- `Junction` – Junction number (1 to 4)
- `Vehicles` – Number of vehicles observed (train data only)
- `ID` – Unique identifier for each row (test data)

## Modeling Approach
I used [Facebook Prophet](https://facebook.github.io/prophet/), a robust open-source time series forecasting model developed by Meta AI, ideal for handling:
- Daily/weekly/yearly seasonality
- Holiday effects
- Uncertainty intervals (prediction bounds)

## Features Engineered
- `hour` – Hour of the day
- `dayofweek` – Day of the week
- `is_weekend` – Flag for weekends
- `custom_festivals` – Important city events (e.g. Diwali, Local Fairs)

## Prophet Settings
- `yearly_seasonality=True`
- `weekly_seasonality=True`
- `hourly` seasonality (custom)
- `holidays` = India public holidays + city-specific festivals

## Visualizations
1) Traffic Forecast with Confidence Interval – Junction 1
Shows predicted vehicle count over time along with upper and lower bounds to account for uncertainty in traffic patterns.

2) Average Vehicles per Day of the Week
Highlights how traffic volume varies across weekdays and weekends, helping identify peak days for each junction.

## Output Format
The final output `SubmissionFile.csv` contains:
- `ID` – Corresponds to test data ID
- `Vehicles` – Forecasted number of vehicles
- `Lower_Bound`, `Upper_Bound` – Confidence interval for traffic prediction
- `Junction` – Junction number (1 to 4)

## My Learnings
- Applied real-world time series forecasting techniques using Prophet
- Learned the importance of seasonal and holiday effects in traffic planning
- Developed dynamic forecasts for multi-source input (per junction)
- Gained experience in data storytelling through simple and effective visualizations

## License
This project is part of an academic internship. Use for educational or non-commercial purposes only.
