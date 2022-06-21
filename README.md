# Amazon_Vine_Analysis

## Overview

The purpose of the analysis is to analyze Amazon reviews written by members of the paid Amazon Vine program and Amazon non-Vine program. 

The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Details of the program can be found here. [Amazon Vine Program Details](https://www.amazon.com/vine/about)

List of Dataset to pick: [https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt)

In this project, I picked the Musical Instruments dataset
[https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Musical_Instruments_v1_00.tsv.gz](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Musical_Instruments_v1_00.tsv.gz)
from the dataset list above and use PySpark on Google Colab to perform ETL process to extract, transform and connect to AWS RDS instance, and load the transformed data into pgAdmin.

After that I used PySpark to determine if there is any bias toward favorable reviews from Vine members and non-vine members in my dataset.


## Result

![review_id_table](https://user-images.githubusercontent.com/100378319/174410942-86f3232e-45ef-4bf2-9474-670aed16a9f7.png)

![product_table](https://user-images.githubusercontent.com/100378319/174410944-87327938-bea7-42db-ba12-1f60e3acd54c.png)

![customers_table](https://user-images.githubusercontent.com/100378319/174410945-c0251240-d053-4fa0-ae8b-2f669d2bcf80.png)

![vine_table](https://user-images.githubusercontent.com/100378319/174410946-7b9c047f-5327-4535-b6a3-05f8f41259d5.png)


Above pictures show after I loaded all four transformed data into pgAdmin

![deliverable_2](https://user-images.githubusercontent.com/100378319/174410950-58e00969-133a-4956-8009-560620a2be0e.png)

1. How many Vine reviews and non-Vine reviews were there?
There are 60 Vine reviews and 14477 non-Vine reviews

2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
There are 34 5-stars review for Vine reviews and 8212 5-stars review for non-Vine reviews

3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
The percentage of Vine reviews were 5-star is 56.67% and 56.72% for non-Vine reviews.


## Summary

After performing the analysis for the dataset, the bias of the Vine member review with the non-Vine member review is negative. Both percentage of 5-star review of total number of reviews are really similar which are 56.67% and 56.72%. (Vine: 34/60 vs non-Vine: 8212 / 14477)

There is couple additional analysis that we could do with the dataset to support my statement:

1. We can perform an analysis on 1-star review to see if there is any bias

2. We can count the number of helpful votes for Vine and non-Vine to see if there is more people tend to seeing the reviews of Vine member 


