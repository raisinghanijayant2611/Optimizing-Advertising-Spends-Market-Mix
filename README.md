# Optimizing Advertising Spends - Market Mix 
 

The client is an Auto Dealer who deals with different brands of various categories ranging from domestic, international, luxury, non-luxury etc. 

The client wants to maximize the ROI on Advertising spends regarding different brands so maximize the profits. Also, since the time period is from 1995-2005, the main channel for Advertising is TV, followed by newspaper, outdoor pamphlets etc. 

To provide a solution, we clubbed different brands into various groups based on business rules defined below. We then ran a multiple regression model on individual cuts with sales as dependent variable and channel advertising as independent variable to evaluate the effect of advertising of each channel on sales for similar segment cars. Following is the summary. 


# Data Wrangling 
We have 10 years of pricing, sales and advertising spends for each brand on an yearly basis. 

The time period is from 1995-2005 

Due to lack of cleanliness and siloed structure of the data, lot of manupulations had to done in order to bind the data together 

However, the values and names are synthetic, jumbled and not real due to privacy purposes, but the trend is kept intact so that the outcomes don't change 

Following are some of the steps that were taken: 
 - Rolling up of different datasets to same level 
 - Formation of business rules for missing values 
 - Outlier treatment using box plots and forming business rules accordingly  
 - Joining multiple datasets at same level to make a master dataset 
 - Combined various channel spends into one as per business rules 
 
 

# EDA: 

Found different cuts as per the business rules as different brands design different cars based on specific audience they want to target.

<b>For example</b>: the company designs luxury cars and mid-size cars differently, catering to different people, and having different specifications. Their selling pattern is also different, and thus they should be advertised differently 

Based on such discussions, formed three cuts and divided the cars accordingly: 

1). Luxury and Non-luxury
2). Domestic and Internation


While running the model at overall level, found out that overall price coefficient was positive, this means the sales of the cars increased with increase in price, which was not quite possible 

Upon further driilling down, figured that it was due to some Brands like Audi, Cadillac etc. which were Luxury models and production of high end versions of cars for some brands, the price coefficient was getting effected (please refer to the image "EDA example" for reference where you can see sales of Audi going up with price, opposite to Ford). 

To make these relations independent, further dummified such brands and year columns to get a correct picture of price correlation on sales 



# Solution: 

In order to solve for market optimization, ran a multiple regression model with sales as the dependent variable and multiple channels and independent variable 
Based on the Beta Coefficient, significance level and std errors, determined which channel is effecting the sales, in what way and how is it performing in comparison to other channels 

Following were the findings: 

1) For Non-Luxury models, the market is more sensitive towards prices as compared to Luxury models

2) Price centric advertisement campaigns are more likely to be effective for non-luxury segment

3) Among the channels, television has the most impact on driving sales across segments

4) For International brands, print media and radio , along with TV are observed to have potential of driving sales

5) By smaller change in price, International brands would be able to capture more sales compared to domestic models; as they are more price sensitive

