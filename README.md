# The Spotify Index

![unnamed](https://user-images.githubusercontent.com/120099114/206535243-492f6ef1-fd32-4691-a32b-b78e376e780a.png)

# Purchasing Power Parity
Purchasing power parity is a concept where the price of a good is measured in different countries to compare the absolute purchasing power of the country. The price of a good would be the same in different countries if there were no transaction costs or trade barriers for that good.

# Why Spotify
Spotify is a audio streaming service and is one of the largest music streaming providers with around 450 million monthly active users and 195 million paying subscribers. It offers digital copyright restricted recorded music and podcasts, which includes more than 82 million songs from record labels and media companies(5). Spotify is avialble in a total of 184 markets including Asia, Africa, Americas, Oceania and Europe; Spotify can be streamed on windows, macos, ios, android and many other devices. I have used spotify for about 7-8 years and thought that it would be interesting to see the pricing differences of a spotify premium subscription in different countries.

# Steps

## 1. Importing the Spotify Subscription Pricing Data 

Source:https://howtospotify.com/spotify-premium-price/

I chose to use countries from the American Continent including countries from both North America and South America. I chose these countries because I wanted to see how the prices differ across North Anerica and South America. In order to webscrape the data, I used the BeautifulSoup method as seen below. I indexed the correct table for The Americas and imported the dataframe table.

![image](https://user-images.githubusercontent.com/120099114/206542459-663751e1-2e21-4f8b-ab0b-1337acc8db2a.png)

![image](https://user-images.githubusercontent.com/120099114/206543429-c0369665-efea-4f35-977e-269aacd89ae0.png)

## 2. Cleaning the data

To clean the data I had to delete unnecessary rows, relabel the columns and convert the price from USD to CAD.

![image](https://user-images.githubusercontent.com/120099114/206544597-dcc7a77f-4f70-4ebf-be6f-d385cc33f691.png)

![image](https://user-images.githubusercontent.com/120099114/206544898-a27fde0c-9df5-4662-8191-0b95e6eda445.png)

## 3. Adding the Country Codes and Tax rates

I hardcoded the sales tax rates and country codes for each country and then added them to the table.

![image](https://user-images.githubusercontent.com/120099114/206545485-fd635292-341a-4fe5-9da9-3d309623f594.png)

## 4. Barplot of Pricing Difference between Canada and other countries

In order to compare the pricing difference between Canada and other American countries I subtracted the price of a Canadian Spotify subscription from the price of a Spotify subscription in other countries. I then added these values to a table and obtained a barplot.

![image](https://user-images.githubusercontent.com/120099114/206546718-02c57a02-388c-4cfd-b19d-0ab9b374f8cf.png)

![image](https://user-images.githubusercontent.com/120099114/206546774-38af3911-44c3-4dca-907a-2e9cfcb0cf50.png)

The US was the only country that had a higher price for a subscription than Canada whereas all other South American Countries and mexico had a lower price for a Spotify subscription. The top 3 lowest Spotify Subscription prices were found in Argentina, Haiti and Brazil with respective prices of $2.7 ,$4.0 and $4.8. Uruguay and Canada had about the same price of $10.8 CAD before taxes which is notable because most other South American countries had lower pricing for a Spotify subscription. This makes sense because Uruguay is one of the most expensive countries in South America.

## 5.External Factor

I chose the GDP or Gross Domestic Product for the external factor to compare Spotify Subscription Pricing. The GDP of a country is the monetary measure of all the consumer goods produced and sold within a specific time period. I chose this factor because I thought that a higher GDP for a country would mean a stronger economy and wealthier population which could then explain the Spotify Subscription pricing. In order to get the GDP data I had to webscrape the data and then clean the data.

![image](https://user-images.githubusercontent.com/120099114/206551092-d6021ae5-2637-475b-8ef2-c5c3d68071b0.png)

![image](https://user-images.githubusercontent.com/120099114/206551295-ec555083-d345-45e7-bace-097ae170d6c5.png)

## 6. External Factor Correlation to Spotify Subscription Pricing

Once I obtained the GDP data I joined the tables for Spotify Pricing and GDP data by the country column. The countries that were in both tables were then displayed along with both the pricing and GDP data.

![image](https://user-images.githubusercontent.com/120099114/206551956-9d281760-de4a-4ef8-ab62-fe65c4b5a538.png)

![image](https://user-images.githubusercontent.com/120099114/206552108-3bdd4cc8-1736-45d5-998d-115e17d6c93f.png)

Once I joined the data I used the correlation function to find the r value or correlation coefficient and also created a scatter plot to visulize the data.

![image](https://user-images.githubusercontent.com/120099114/206552844-664606d1-bff7-4cd8-bbde-899f3ea8dfb6.png)

The scatterplot showed a weak trend between pricing and gdp for a country.

![image](https://user-images.githubusercontent.com/120099114/206552934-6f3829d4-8844-4a35-844f-d6483aeb9e5e.png)

I found an correlation coefficient of 0.52 which means that the GDP of a country and the pricing of a Spotify subscription are moderately correlated. I think that the correlation coefficent could have been stronger if there were more wealthy countries included in the index.

## Data Sources:

1.Spotify Subscription Prices
https://howtospotify.com/spotify-premium-price/

2.Sales tax
https://tradingeconomics.com/country-list/sales-tax-rate

3.GDP information
https://www.worldometers.info/gdp/gdp-by-country/

4.PPP
https://en.wikipedia.org/wiki/Purchasing_power_parity

5.spotify
https://en.wikipedia.org/wiki/Spotify

6.GDP
https://en.wikipedia.org/wiki/Gross_domestic_product
