# Video Games AWS Project

### Dashboard Link : 

### Data Source: ODBC & Amazon Athena 

## Problem Statement
The video game industry generates large volumes of sales data across platforms, genres, publishers, and regions. Analyzing this data efficiently at scale poses challenges for traditional on-premise tools. The goal of this project is to leverage AWS infrastructure — specifically S3 for storage and Athena for querying — to perform structured analysis on historical video game sales and extract meaningful insights about top-performing titles, platforms, and publishers in the North American market.


### Steps followed 

- Step 1: Set up an AWS account, create an Amazon S3 bucket, and upload the Video Games dataset (CSV file) to the bucket for storage and further analysis.
<img width="1334" height="501" alt="Image" src="https://github.com/user-attachments/assets/f7c3a06e-0d8f-4184-ad94-b3b741a00ebf" />

- Step 2: Executed SQL queries using the Amazon Athena Query Editor on the dataset as demonstrated below.

		SELECT * FROM "mypowerbidb"."pbiprojectaws" limit 10;
	
<img width="959" height="478" alt="Image" src="https://github.com/user-attachments/assets/2337ed09-c7d1-4a73-98b5-412d3569fca0" />


- Step 3:
