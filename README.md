# Predicting Wildfires in California: A Decision-Support Tool for Firefighters & Emergency Planning


# Project Overview
Wildfires in California have increased in frequency, intensity, and impact, placing immense pressure on firefighting resources and emergency response systems.This project builds a machine learning–based wildfire prediction system designed to support firefighters and emergency planners by answering two critical questions:
- When are wildfires likely to start?
- How severe might the resulting fire be?
- The goal is not automation, but decision support, helping fire agencies allocate resources earlier, prepare for high-risk periods, and reduce response time.

# Objectives
- Predict wildfire occurrence using weather and environmental conditions
- Estimate potential fire damage size once a fire occurs
- Engineer interpretable, fire-relevant risk features
- Prioritize recall to avoid missed fire events
- Build a framework suitable for operational use with human oversight

# Data Sources
- California Weather and Fire Prediction Dataset
- California Fire Perimeters Dataset


# Data Preprocessing
- Converted all date fields to datetime
- Removed duplicate records
- Dropped rows with missing fire start dates
- Filled missing weather values using monthly–yearly means
- Preserved outliers intentionally (extreme conditions are critical for fire prediction)

# Feature Engineering
- Threshold-Based Features
- Precipitation
- Maximum temperature
- Minimum temperature
- Average wind speed
- Temperature range
- Lagged precipitation
- Interactive & Non-Linear Features
- Lagged precipitation × max temperature (delayed rain effect)
- Lagged wind × max temperature (persistent heat & wind)
- Wind × precipitation (wind during rainy days)
- Min temperature × precipitation (overnight moisture retention)
- Fire-Specific Risk Indicators
- Days without rain (drought stress)
- Heat wave detector
- Extreme fire weather (hot + dry + windy)

  
These features were designed to reflect real-world fire behavior, not just statistical patterns.

# Modeling Approach
Two separate prediction tasks were modeled:
- Model 1: Fire Occurrence Prediction

Binary classification: Predicts whether a wildfire will occur

- Model 2: Fire Damage Size Prediction

Multi-class classification: Predicts severity category once a fire starts


# Validation Strategy
- Temporal 80–20 train/test split
- Tested explicitly on future data
- Cross-validation
- Multiple performance metrics


# Future Improvements
- Fire severity metrics (spread rate, duration, burn intensity)
- Spatial features (latitude, longitude, elevation, slope)
- Terrain and fuel load data
- Human activity indicators (roads, power lines, agriculture)
- Spatial risk heat maps
- Resource needs prediction (personnel, aircraft, equipment)

Black-box concerns for complex models

Legal and accountability implications in emergency settings
