# I Just Want To Be Popular...On Airbnb

Example of how to add a picture --> ![alt text](https://raw.githubusercontent.com/username/projectname/branch/path/to/img.p)


## Overview
I Just Want To Be Popular is a data science project on predicting popularity of Airbnb listings in San Francisco in 2017. Will a listing be in the top 20 percent?
The proxy for popularity is "reviews per month".


## Motivation
Airbnb hosts want their listings to be popular to increase the number of bookings they receive and therefore increase profits. 
This project serves to extend some answer to what hosts should do to become more popular. 


## Data

Data Source:
InsideAirbnb.com

Date Scope:
The data set used in this project consists of 117,107 total listings in 2017. There are approximately 8,000-16,000 listings per month. 


## Baseline

Baseline 1: Guess that every listing is "not popular"

Baseline 2: Randomly guess “popular” (20% of the time) and “not popular” (80% of the time)

The scores above were determined from 1,000 trials. You can find the code for this in Baseline_Score.ipynb.

Baseline 3: Guess that every listing that was popular this month will be popular next month

## Analysis:

Model A: TEXT FEATURE
This model is specifically for the description of the listing. 


Run Text Vectorizer TF-IDF
  I removed the English stopwords

Model B: NON-TEXT FEATURES


## Findings:
(Insert feature importance pictures and description)
  
  
## Instruction:

  
