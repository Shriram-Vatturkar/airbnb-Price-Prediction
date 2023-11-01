# Airbnb Insights: Predictive Booking Analysis 
Tourism is rapidly growing at an unprecedented rate, especially after the COVID era. It has undergone significant changes in the past years where the traditional concept of staying in a hotel doesn't entertain tourists anymore. Tourists have started exploring more options that allow freedom of travel and comfortable accommodation at a reasonable price. Airbnb is a popular online marketplace that connects property owners with travelers who are looking for short-term accommodations. It has transformed the way people find and book places to stay while traveling for various purposes, including vacations and business trips. It provides quick and easy access to passive income for homeowners who can't rent out their property for the long term but can provide quick accommodations to tourists whenever their property is available. 

Our project aims to help these homeowners understand the analytics of this marketplace and make informed decisions to maximize their business profit. We are providing the user with useful insights into this market and provide a platform where the user will be able to understand the chances of his property being booked based on various factors.

### Dataset Description

[shriramvatturkar22071206107.ipynb - Colaboratory.pdf](https://github.com/Shriram-Vatturkar/airbnb-Price-Prediction/files/13230833/shriramvatturkar22071206107.ipynb.-.Colaboratory.pdf)
![WhatsApp Image 2023-11-01 at 11 44 44 PM](https://github.com/Shriram-Vatturkar/airbnb-Price-Prediction/assets/140342007/3202122f-a8d3-4823-8d41-ba3492d918fa)


The dataset contains 15 columns and 400 rows.

### Dataset Collection ###
We have collected the data by scraping it from the Airbnb website using the Apify data scraping tool.

![WhatsApp Image 2023-11-01 at 11 44 38 PM](https://github.com/Shriram-Vatturkar/airbnb-Price-Prediction/assets/140342007/d5cb2b57-c980-42af-b4ac-6fedb1be60dd)

### Data Preprocessing ###

Removing Unnecessary Columns: 
```
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

```

### Changing the Column Indexes to the Desired Position
```
df = df.reindex(columns=change_column)
df.head(3)
```

### Renaming Columns
```
df.rename(columns = {'pricing_info/cancel_policy/name' : "cancel_policy", "pricing_quote/primary/price" : "pricing"}, inplace = True)
```
### Checking for Null Values in the Data and Removing them
```
df.isnull().sum()
df.dropna(inplace = True)
```
### Merging all the processed datasets together
```
data = pd.concat([df, df_sec, df_third, df_fourth, df_fifth], ignore_index=True)
```
