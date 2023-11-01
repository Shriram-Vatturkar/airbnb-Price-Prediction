# Airbnb Insights: Predictive Booking Analysis  
Tourism is rapidly growing at an unprecedented rate, especially after the COVID era. It has undergone significant changes in the past years where the traditional concept of staying in a hotel doesn't entertain tourists anymore. Tourists have started exploring more options that allow freedom of travel and comfortable accommodation at a reasonable price. Airbnb is a popular online marketplace that connects property owners with travellers who are looking for short-term accommodations. It has transformed the way people find and book places to stay while travelling for various purposes, including vacations and business trips. It provides quick and easy access to passive income for homeowners who can't rent out their property for the long term but can provide quick accommodations to tourists whenever their property is available. 

Our project aims to help these homeowners understand the analytics of this marketplace and make informed decisions to maximize their business profit. We are providing the user with useful insights into this market and provide a platform where the user will be able to understand the chances of his property being booked based on various factors.

### Dataset Description

![WhatsApp Image 2023-11-01 at 11 44 44 PM](https://github.com/Shriram-Vatturkar/airbnb-Price-Prediction/assets/140342007/3202122f-a8d3-4823-8d41-ba3492d918fa)


The dataset contains 15 columns and 400 rows.

### Dataset Collection ###
We have collected the data by scraping it from the Airbnb website using the Apify data scraping tool.

![WhatsApp Image 2023-11-01 at 11 44 38 PM](https://github.com/Shriram-Vatturkar/airbnb-Price-Prediction/assets/140342007/d5cb2b57-c980-42af-b4ac-6fedb1be60dd)

## Data Preprocessing 

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

## Data Analysis

### Visualizing the Dataset on a map 

We have visualized the entire dataset on an interactive map to show the locations of the properties and their price density.

![Screenshot 2023-11-02 005737](https://github.com/Shriram-Vatturkar/airbnb-Price-Prediction/assets/140342007/50838cb3-a2cc-427d-9ba5-c5073eae12bc)

The majority of properties which lie in the higher price range are found in Mumbai while rent in Pune seems to lie in the lower range of the price spectrum comparatively.

## Distribution of States
![Screenshot 2023-11-02 010647](https://github.com/Shriram-Vatturkar/airbnb-Price-Prediction/assets/140342007/eefd55f0-85f9-4240-ba5d-1c9be45bd700)
From the visualized pie chart we can infer that the majority of properties in the dataset lie in Maharashtra while the least are from Goa.
Telangana and Karnataka have same number of properties in the data.

## Type of property
![Screenshot 2023-11-02 011128](https://github.com/Shriram-Vatturkar/airbnb-Price-Prediction/assets/140342007/e8304edc-bfc2-43fd-abe9-9fa9db8cc4d2)
The majority of the properties listed in the dataset are entire homes, followed by private rooms. Only a fraction of them are hotel/college rooms.

## Bedrooms per room type
![Screenshot 2023-11-02 012051](https://github.com/Shriram-Vatturkar/airbnb-Price-Prediction/assets/140342007/a4c4641e-8039-4bf6-8126-58b131c93497)
The majority of the properties being listed have either one-bedroom or two-bedroom facilities. 

## Correlation Heatmap
![Screenshot 2023-11-02 012424](https://github.com/Shriram-Vatturkar/airbnb-Price-Prediction/assets/140342007/6fe9d32e-7a88-472b-82fb-c957608cea6d)

