# Amazon_Vine_Analysis

## Overview
Data analysts were tasked with analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

Data from Amazon's Lawn and Garden department was analyzed to determine if having a paid Vine review makes a difference in the percentage of 5-star reviews.  The Extract, Transform, and Load (ETL) process was used on the Amazon Lawn and Garden dataset.  An AWS RDS database was create and the Lawn and Garden dataset was uploaded into an S3 bucket.  pgAdmin was utilized to connect to AWS, and pySpark and postgreSQL were used against the data set to create four separate DataFrames to match the table schema in pgAdmin.  The transformed data was then uploaded into AWS RDS. 


## Resource
- AWS                     
- RDS                     
- S3                      
- Python                  
- pySpark    
- pgAdmin  
- Jupyter Notebook
- Google Colaboratory
- Pandas        
                 

## Results
The Vine table was exported from pgAdmin and Python Pandas was used against the data.  The Vine table contained 1,048,575 rows of data.

![Vine_table_csv](https://user-images.githubusercontent.com/73897240/112730388-a7576e00-8f07-11eb-8724-bf0540f1a1b4.PNG)


The Vine table data was transformed to show only reviews where there were 20 or more reviews for the product.  This new Pandas DataFrame reduced the dataset to 8,488 rows of Lawn and Garden Amazon reviews.

![helpful_votes_df](https://user-images.githubusercontent.com/73897240/112730437-ef769080-8f07-11eb-9e89-9557b718103e.PNG)


This data set was further reduced to show only rows where helpful_votes was greater than or equal to 50% of helpful_votes divided by total_votes.  This gave 7,801 rows.  The parameters used against the Vine table resulted in a 99% reduction in data.

![better_helpful_df](https://user-images.githubusercontent.com/73897240/112730510-585e0880-8f08-11eb-9be0-cebb079458bb.PNG)


Two new Pandas DataFramse were created to retrieve all rows where the review was part of the Vine program and to retrieve all rows where the review was not part of the Vine program.  This resulted in 91 paid reviews and 7,710 unpaid reviews.

![](https://user-images.githubusercontent.com/73897240/112730588-c86c8e80-8f08-11eb-80e2-95a9584d635f.PNG)  |  ![](https://user-images.githubusercontent.com/73897240/112730710-72e4b180-8f09-11eb-872c-d022225c26f8.PNG)


## Summary
Based on analysis of the sample selected from the Amazon Lawn and Garden reviews, Vine reviews did not appear to affect 5-star reviews.  There were slightly more 5-star reviews from unpaid reviews.

Additional analysis should be conducted against multiple Amazon review datasets, with the same parameters that were used against the Lawn and Garden dataset.  Other datasets could show that Vine reviews are more likely to give 5-star product reviews.  It would also be interesting to determine if male or female are more likely to leave a review in general versus how likely are they to leave a 5-star review as a Vine member or unpaid reviews.  

Thank you for your time,

John
