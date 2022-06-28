# Amazon_Vine_Analysis
Big Data using PySpark, Amazon Web Service (AWS), Google Colaboratory, and pgAdmin.

## Overview
The purpose of this project is to analyze Amazon reviews written by members of the paid Amazon Vine program, a service that allows manufacturers and publishers to receive reviews of their products and determine if there are any biases between Vine members and Non-Vine member's reviews.

Companies that will pay a fee to Amazon and may provide free products to Vine members who are then required to publish a review. In order to determine if there is any bias towards favorable reviews from Vine members vs. non-members, we need to identify the percentage of 5 star ratings to total rating. As part of this exercise, we were asked to choose from 50 datasets to extract, transform and load into a dataframe in order to complete our analysis. Throughout this analysis, we used Using PySpark to perform ETL, the analysis extracts the dataset, transforms the data, connects to an AWS RDS instance, loads the transformed data into pgAdmin.

### Steps Involved
- Define big data and describe the challenges associated with it.
- Define Hadoop and name the main elements of its ecosystem.
- Explain how MapReduce processes data.
- Define Spark and explain how it processes data.
- Describe how NLP collects and analyzes text data.
- Explain how to use AWS Simple Storage Service (S3) and relational databases for basic cloud storage.
- Complete an analysis of an Amazon customer review.

## Result
### Deliverable: 1
- Created dataframes using "https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Digital_Video_Games_v1_00.tsv.gz" <br>
 ![DF1](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/CustomerTableDf.PNG)<br>
 ![DF2](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/ProductDf.PNG)<br>
 ![DF3](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/ReviewDf.PNG)<br>
 ![DF4](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/Vine.PNG)<br>
- Created the table for customers_table, products_table, review_id_table and vine_table in AWS RDS <br>
 1. customers_table<br>
 ![Table1](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/TableCustomer.PNG)<br><br>
 2. Products_table <br>
 ![Table2](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/TableProduct.PNG)<br><br>
 3. Review_id_table<br>
 ![Table3](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/TableReview.PNG)<br><br>
 4. Vine_table <br>
 ![Table4](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/TableVine.PNG)<br><br>
 - All the four tables are exported as csv files in the [Resources Folder](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/tree/main/Resources)<br>
 
### Deliverable: 2
- How many Vine reviews and non-Vine reviews were there? <br>
  The dataset appears a little on the small side for Big Data with 145,431 reviews. Only reviews with 20 or more votes where considered for the rest of the analysis leaving 3,342 reviews. Helpful votes were defined as being 50% or greater than the total votes narrowing the list to 1,685 reviews.

  Unfortunately, due to the applied criteria, it significantly diminished the sample size. In the remainder 1,685 reviews, there were no reviews that were paid for by the Vine program. <br>
All 1,656 remaining reviews are unpaid Vine with 0 paid Vine. Please find the screenshot beow <br>
  ![Paid](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/Paid.PNG)<br><br>
- How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars? <br>
   As for 5-star unpaid Vine reviews, there were 631 reviews and 0 paid Vine with 5-star reviews.<br>
  ![UnPaid](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/UnPaid.PNG)<br><br>

- What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars? <br>
  The percentage of unpaid, 5-star Vine reviews resulted in 37.4%, while the percentage of paid, 5-star Vine reviews would be 0%.<br>
  ![PercentageUnPaid](https://github.com/ashwinihegde28/Amazon_Vine_Analysis/blob/main/Resources/images/PercentageUnPaid.PNG)<br><br> 
  
## Summary
  - Because the sample size was constricted to a degree that it was impossible to compare paid and unpaid Vine reviews, the analysis is biased towards unpaid Vine     reviews. Another indicator is comparing 37% of unpaid, 5-star Vine reviews to 0% paid, 5-star Vine reviews also shows that the unpaid Vine are biased as well.
  - In addition, 
    1. Running the same analysis using datasets from different product categories can provide us with the whole picture of whether reviews made by Vine members are bias.
    2. The starting criteria of 20 likes or the 50% helpful criteria may have been too high, which made the data set too small. Adjustments to these criteria is a first step to reconsidering using this data set.



 
