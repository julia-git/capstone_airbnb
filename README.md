# I Just Want To Be Popular...On Airbnb

![Home](/img/home.jpg)

## Overview
I Just Want To Be Popular is a data science project on predicting popularity of Airbnb listings in San Francisco in 2017. Will a listing be in the top 20 percent?<br />


The proxy I used for popularity is "reviews per month".


## Motivation
Airbnb hosts want their listings to be popular to increase the number of bookings they receive and therefore increase profits. 
This project serves to extend some answer to what hosts should do to become more popular. 


## Data

Data Source:
InsideAirbnb.com

Date Scope:
The data set used in this project consists of 117,107 total listings in 2017. There are approximately 8,000-16,000 listings per month. 


## Baseline


![Baseline](/img/Baseline_Scores.png)

<br />
The scores in baseline 2 were determined from randomly guessing with 1,000 trials. The code for this can be found in Baseline_Score.ipynb.

## Analysis:

Model A: TEXT FEATURE<br />
This model is specifically for the description of the listing.<br />
After removal of the English stopwords and lemmatization of the text, I ran the text through the CountVectorizer and the TF-IDF. The best model for predicting popularity was Random Forest with the CountVectorizer, which gave me a F1 score of 0.86.<br />
The code for Model A can be found in Model_A.ipynb.

Model B: NON-TEXT FEATURES<br />
The features I used includes 'host_length', 'amenities_count', 'review_scores_rating', 'host_response_rate', 'access_filled', 'house_rules_filled','space_filled','accommodates', 'extra_people', 'price_per_guest', 'price_per_bedroom','guests_included', 'host_about_filled', 'cancellation_policy', 'room_type', 'property_type_new', 'instant_bookable', 'calculated_host_listings_count', and  'minimum_nights'. A description of these features can be found in Appendix A below. <br />
<br />
XGBoost was my best model, with an F1 score of 0.88.<br />
The code for Model B can be found in Model_B.ipynb.<br />

Final: <br />
My final model is an ensemble model of both the text and non-text features. My goal is to ensemble the best models. I was able to produce an ensemble model with the second best model from Model A and the best model from Model B, and am currently in progress with preparing an ensemble model with the best model from Model A. 

My current ensemble model predicted with a recall score of ~94%, precision score of ~86%, f1 score of ~90%. This model was able to better identify popularity of listings relative to the baseline recall score of ~88%. The code for the final model can be found in Ensemble.ipynb.

## Findings:
These are the top words in the description of the listing that the model used to identify popularity.

![ImportantWords](/img/Top_Words.png)

These are the top five features identified by the model as the most important. 

![ImportantFeatures](/img/Average_Permutation.png)

Given the findings, here is a sample text that I put together for what would be a good description for a listing. The words in blue are the key words that the model used to identify as popular (see word cloud above).

![Sample](/img/Sample_Description.png)

## Appendix A: Description of features

  host_length - years that the host has been hosting<br />
  amenities_count - the number of amenities the host offers for the listing<br />
  review_scores_rating - review score for the listing<br />
  host_response_rate - responsiveness of the host<br />
  access_filled - is there a description under the access category (yes or no)<br />
  house_rules_filled - is there a description under the house rules category (yes or no)<br />
  host_about_filled is there a description under the host about category (yes or no)<br />
  space_filled - is there a description under the space category (yes or no)<br />
  accommodates - the number of people the place accomodates<br />
  extra_people - the number of extra people that the place can accomodate<br />
  price_per_guest - the log of the listing price plus cleaning fee per number of guests<br />
  price_per_bedroom - the log of the listing price plus cleaning fee per number of bedrooms<br />
  guests_included - the number of guests included with the listing price<br />
  cancellation_policy - the kind of cancellation policy<br />
  room_type - the type of room<br />
  property_type_new - the type of property<br />
  instant_bookable - is this place instantly bookable (yes or no)<br />
  calculated_host_listings_count - the number<br />
  minimum_nights - the minimum number of nights one must stay to book the place<br />
