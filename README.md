# Airbnb Insights: Predictive Booking Analysis 
Tourism is rapidly growing at an uprecedented rate especially after post covid era. It has undergone significant changes in the past years where the traditional concept of staying in a hotel doesn't entertain tourists anymore. Tourists have started exploring more options which allow freedom of travel and comfortable accomodation at a reasonable price. Airbnb is a popular online marketplace that connects property owners with travelers who are looking for short-term accommodations. It has transformed the way people find and book places to stay while traveling for various purposes, including vacations and business trips. It provides a quick and easy access to pasive income for home owners who can't rent out there property for long term but can provide quick accomodations to tourists whenever their property is avaiable. 

Our project aims to help these home owners understand the analytics of this marketplace and make informed decisions to maximize their business profit. We are providng the user with useful insights into this market and provide a platform where user will be able to understand the chances of his property being booked based on various factors.

#Dataset Description#

<img width="836" alt="WhatsApp Image 2023-11-01 at 11.44.44 PM" src="https://github.com/NehalNetha/Mental-Health_Analysis/assets/84872197/6cca047d-3e48-4f71-bbd7-c47fba6d4971">

The dataset contains of 15 columns and 400 rows.

#Dataset Collection#
We have collected the data by scraping it from the airbnb website using Apify datascraping tool.

###Data Preprocessing###

Dropping Uneccessary Columns: 
'''
df.drop([
    "picture/url",
    "pictures/contextual/0/id",
    "pictures/contextual/0/messages/0",
    "pictures/contextual/0/url",
    "pictures/contextual/1/id",
    "pictures/contextual/1/messages/0",
    "pictures/contextual/1/messages/0",
    "pictures/contextual/1/messages/1",
    "pictures/contextual/1/url",
    "pictures/contextual/2/id",
    "pictures/contextual/2/messages/0",
    "pictures/contextual/2/messages/1",
    "pictures/contextual/2/url",
    "pictures/contextual/3/id",
    "pictures/contextual/3/messages/0",
    "pictures/contextual/3/messages/1",
    "pictures/contextual/3/messages/2",
    "pictures/contextual/3/messages/3",
    "pictures/contextual/3/url",
    "pictures/contextual/4/id",
    "pictures/contextual/4/messages/0",
    "pictures/contextual/4/messages/1",
    "pictures/contextual/4/messages/2",
    "pictures/contextual/4/messages/3",
    "pictures/contextual/4/url",
    "pictures/contextual/5/id",
    "pictures/contextual/5/messages/0",
    "pictures/contextual/5/messages/1",
    "pictures/contextual/5/messages/2",
    "pictures/contextual/5/messages/3",
    "pictures/contextual/5/url"
], axis=1, inplace =True)
'''
