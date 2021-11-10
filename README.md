# Zillow Time Series Modeling: Texas 
Authors: 
- Lorela Blaka
- Seth Kaufman
- Rashid Karriti

# Overview
![https---specials-images forbesimg com-dam-imageserve-1091770016-960x0 jpg?fit=scale](https://user-images.githubusercontent.com/82670256/136472341-8f62454c-20bc-4df1-abc1-e6ab32aa90e9.jpeg)

This project analyzes several of time series models to provide a real estate investment firm who would like to break into the Texas housing market. Based on a series of filtering, we found that the top 5 zip codes are:  
- 76108: Fort Worth (Dallas area)
- 75052: Grand Prairie (Dallas area)
- 75104: Cedar Hill (Dallas area)
- 77571: La Porte (Houston area)
- 79423: Lubbock (Northern area)

![tejas](https://user-images.githubusercontent.com/82670256/136484300-b6cab662-0eef-4af2-8a60-f2b49a37fd69.PNG)

# Business Understanding
As independent real estate consultants, we have been contracted by Texas Real Estate Investments (TREI) to find the top 5 zip codes they should invest in that would offer them the greatest investment success. Based on our client's requests, we found that looking at the Affordability Score (a score representing the ability of a home buyer to pay their mortgage), and average Return on Investment(ROI) in a given zip code are strong indicators of whether a homes in those areas are worth investing in for TREI. Our task is to identify what these top 5 zip codes are based on our predictions through several Time Series models and present our findings to the client. 

# Data Understanding, Preparation, and Modeling 
The project utilizes Time Series Models, specifically focused on ARIMA and SARIMAX models, running several iterations on the models to see within what range our models can capture the best prices of the zip codes. The data provided to us was from the Zillow Housing Data spanning from 1996 to 2018 with about 14,000 Zip codes within the United States, which after filtering down to specifically Texas we are left with 1,839 zip codes to filter through. Our other dataset comes from Missouri Census Data Center, Median Family Income (2019) that provided us insight to calculating our Affordability Score. After further filtering, we narrowed down our cities based on a population above the 75th percentile, looking at median prices of a home across the state over time. 

![Unknown-1](https://user-images.githubusercontent.com/82670256/136558177-d65ae03c-345e-43c8-936e-e3ec4874b4f4.png)

# Results
After narrowing down our top 5 zip codes, we began to look at what the Average ROI of each given zip code looks like. We found that all of the ROI's of the top 5 zip codes was significantly larger than the average ROI across all zip codes in Texas. This further suggests that these zip codes are some of the best zip codes across the state. 

![Unknown](https://user-images.githubusercontent.com/82670256/136482733-73546361-3a38-4675-a6fe-1b6012122bbd.png)
 
Furthermore, when looking at the time series of what the average affordablity score was across all zipcodes in the state were above the 80th percentile and specifically looking at the average affordability score in each given zip code. We found that our top five zip codes have some of the best scores across the state. This ensures that TREI can trust that in these 5 zip codes there is a greater chance that home buyers will be able to pay off their homes, with a lower affordability score being better. 
![Unknown-2](https://user-images.githubusercontent.com/82670256/136482764-9d5a619f-b2af-4f79-b2fc-f56ea49e6259.png)

After analyzing pricing behaviors for each zip code and noticed mainly linear upward trends, we used 1996-2015 prices to train our model, so it can predict 2016-2018 prices. Subsequently, we conducted a series of optimizations of our ARIMA models for each of the zip codes and manually testing the hyperparameters for each zip code in the SARIMAX, we found that we can predict that a price increase will occur overtime. Our best performing model for a singular zip code was ARIMA Model as seen below. 

![image](https://user-images.githubusercontent.com/82670256/136583120-3e51892a-8b1e-4d09-8655-61b7521f3aca.png)

<img width="654" alt="Screen Shot 2021-10-08 at 11 37 02 AM" src="https://user-images.githubusercontent.com/82670256/136584921-5c7f14a0-5146-4cc9-a961-b36d767ce23f.png">

Lastly, across all zip codes, our test and train root mean squared error (RMSE) prediction were off by $6,500 on average. Below you can see the root mean squared error for each zip code. 

| Zip Code | Model | Train RMSE | Test RMSE | 
| :---: | :---: | :---: | :---: | 
| 75052 | ARIMA | $7,295 | $4,572 | 
| 75104 | SARIMAX | $8,088 | $8,363 | 
| 76108 | ARIMA | $5,920 | $8,480 | 
| 77571 | SARIMAX | $6,227 | $8,722 | 
| 79423 | SARIMAX | $5,153 | $2,420 | 

# Conclusion & Future Steps
TREI should invest in homes in the top 5 zip codes in the given areas we prove to be the best place for long-term investment success, based on our Affordability Score and ROI. 

For a more comprehensive evaluation for TREI to find future to find more zip codes that have investment successes we should inquire into:
- Expanding the model to work for other states.
- Get the model to forecast for more than a few years. 

# Project Structure
  ```
├── data  <-- CSVs
├── images 
├── working notebooks       <--- Directory for individual workspaces
│   ├── seth
│   ├── lorela
│   ├── rashid
├── README.md
├── TimeSeriesPresentation.pdf   <-- non-technical presentation slides
├── final_nb.ipynb    <-- Jupyter Notebook containing codes detailing project's analysis 
└── .gitignore
```
