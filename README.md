# Amazon Vine Analysis

## Project Overview
In this project I created an AWS RDS database and four tables in pgAdmin into which I loaded my transformations of a dataframe set up from a dataset taken from one of the Amazon Review datasets (in this case, music).  I then used one of the transformed dataframes (the one related to the Vine program) and further modified it to see if bias towards the Vine reviews existed.

## Results
Before I created the DataFrames displaying the number of Vine reviews vs. the number of regular reviews, I removed all rows where the total number of votes was less than 20, plus the rows where the percentage of helpful votes was less than 50%.

### Vine reviews

![Vine reviews](https://github.com/MaxV6ft4/Amazon_Vine_Analysis/blob/main/Screenshots/Vine_reviews.png)

- Unfortunately in this music dataset, after the multiple filters I discovered that there were only seven total Vine reviews.
- Furthermore, of those reviews, none of them were five-star reviews.  All were either three or four stars.
- Therefore, the percentage of reviews being five-star was zero.

### non-Vine reviews

![non-Vine reviews](https://github.com/MaxV6ft4/Amazon_Vine_Analysis/blob/main/Screenshots/other_reviews.png)

- There was a total of 105,979 non-Vine reviews.
- Of those reviews, 67,580 were five-star reviews.
- The percentage of non-Vine five-star reviews was 64%.

## Summary
Clearly, positivity bias does not exist in this particular dataset.  Without the filtering, there would probably be a lot more five-star Vine reviews, but these could have had either very few total votes or many non-helpful votes, thus not making it past the filtering process.  64% of non-Vine reviews being five-star is very normal and does not at all infer positivity bias.   To help get a better picture of Vine reviews (if the number were higher), I'd perform one more filter on the original dataframe that only gets rows with verified purchases.  Verified purchases mean that the customer bought it directly from Amazon and did not receive a discount by buying it used from an independent seller on Amazon.  That way all the five-star Vine or non-Vine reviews will only be written about purchases through Amazon itself, eliminating potential positivity bias due to price.
