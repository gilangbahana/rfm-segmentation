# New York City (NYC) Airbnb Listings Segmentation using RFM Analysis

## Overview / Case Background
Airbnb is an online marketplace which provides homestay or tourism services. Airbnb presence disrupts hotel and inns market. New York City is no exception. NYC is the most populous city in US, center of finance, media, government, research, and technology. NYC is also the biggest revenue generator for Airbnb in the US, because there are always traveler going to NYC, and the amount of listings of NYC Airbnb is the largest in US. The **occupancy rate of Airbnb in NYC is only 50%**, compared to its direct competitor, hotel, is around 90% in 2019. Then, Covid-19 hits in 2020, and **Airbnb is also affected by -56% yoy** decreasing of traveler's stay in 2020. We're assigned to **increase traveler's stay in Airbnb to +40% yoy in 2021** by **maximing high performance listings and giving recommendation to low performance listings** by the end of 2021.

![alt text](nyc-airbnb-business-question.JPG)

## Possible Causes

![alt text](https://github.com/gilangbahana/rfm-segmentation/blob/main/nyc-rca.JPG)

## Data Source
1. [listings_dataset](https://drive.google.com/file/d/1u98aNFkoMSh-wO973HG9rl57MhCUJJCD/view?usp=sharing).
2. [reviews_dataset](https://drive.google.com/file/d/10NbikSxI_GtZsTxVmx6_hcIpAwvH5RMj/view?usp=sharing).

## Data Preparation and Cleaning
1. Not all columns will be selected for analysis process, only columns with related information will be used.
2. Check for missing value, data types, duplicate values, invalid values, and outliers.
3. Renaming columns name for clarity purpose.
4. Create additional columns (variables) to be used for analysis later (`Recency`, `Frequency`, `Monetary`)
5. Join all required column and table to one dataframe named as dfco, using merge functions in python.

## EDA Process
In this process, we find initial insights, such as:
1. Manhattan has the most total room available in NYC Airbnb listings, followed by Brooklyn, Queens, Bronx, and Staten Island.

![alt text](https://github.com/gilangbahana/rfm-segmentation/blob/main/nyc-eda-based-on-borough.JPG)

2. Entire home/apartement type of listings is very dominant in NYC Airbnb listings, primarily in Brooklyn and Manhattan borough. While Private Room is dominant in Queens, Hotel Room and Shared Room only show very little percentages in five neighbourhoods.

![alt text](https://github.com/gilangbahana/rfm-segmentation/blob/main/nyc-eda-based-on-room-type.JPG)

3. Total Airbnb beds only 32% of total hotel bed / inns in NYC. With total visitors to NYC is 66.6 mil on 2019. 

![alt text](https://github.com/gilangbahana/rfm-segmentation/blob/main/nyc-eda-airbnb-beds-2019.JPG)

## Listing Segmentation using RFM Analysis
For RFM analysis (Recency, Frequency, Monetary). Following columns will be use for references:
1. `Recency` for Recency Score
2. `Frequency` for Frequency Score
3. `Monetary` for Monetary Score

![alt text](https://github.com/gilangbahana/rfm-segmentation/blob/main/nyc-rfm-initial.JPG)

After columns ready to be analysed, create a ranking based on those column, and normalize the rank of the listings.

![alt text](https://github.com/gilangbahana/rfm-segmentation/blob/main/nyc-rfm-ranking.JPG)

For scoring method:
We are going to rate the listings on a scale of 5, based on their normalized value. Then, we store the data in a new created column named RFM_Score_Total. Formula used for calculating RFM score total is `0.15*Recency Score + 0.28*Frequency Score + 0.57*Monetary Score`

![alt text](https://github.com/gilangbahana/rfm-segmentation/blob/main/nyc-rfm-score-total.JPG)

And we can summarize the listings segmentation and description as below

![alt text](https://github.com/gilangbahana/rfm-segmentation/blob/main/nyc-rfm-summary.jpeg)

## Analysis Insight
From the listings segmentation, we got some points

- Price of top listings on average 10% lower than other listing segment. 
- Top listing generally offers their room for daily stay, while low or lost listing offers their room only for monthly stay.
- We can book on average 168 days in advance for top listings, while for lost listings we can book none (which means maybe the lost listings is closed permanently).
- Low listings only give the traveler booked their listings one month in advance.
- There’s no difference between all listings in terms of room type. Most wanted room type in every segment is entire home/apt.

## Recommendation
In order to bounce back faster in 2021, we have to focus on our Top Listings, while at the same time, applying top listings characteristics to low performance listings. 

### For Top Listings
- This is our revenue generator, we have to give ads placement in first page when traveler searching for nearby listings.
- Creating promotional video for top listings using famous influencer.
- Creating monthly or weekly discount for traveller if they stay longer (more than 3 days) in top listings.
- Creating campaign competition for listings to achieve as much traveler as they could get. 

### For All Listings
- Campaign for seasonal time (for example: National Holiday).
- Creating guidebook/guestbook to tell the traveller everything they can do in the area.
- Creating loyalty point program for traveler (for example `platinum`, `gold`, `silver`.

#### Presentation Deck
[Airbnb Listings Segmentation using RFM Analysis Deck ](https://github.com/gilangbahana/rfm-segmentation/blob/main/New%20York%20City%20(NYC)%20Airbnb%20Listings%20Segmentation%20using%20RFM%20Analysis.pdf)
