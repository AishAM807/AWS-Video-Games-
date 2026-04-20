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


- Step 3: Set up an IAM user account to enable secure access control and resource management.

<img width="898" height="503" alt="Image" src="https://github.com/user-attachments/assets/17ef9a5c-a64b-4a05-8d0f-de652b80d4f6" />


<img width="698" height="255" alt="Image" src="https://github.com/user-attachments/assets/ff7db5d2-d603-4deb-baf6-3d8701e112b5" />

- Step 4: Successfully downloaded and installed the Simba connector to enable connectivity with Amazon Athena.

- Step 5: Imported data into Power BI Desktop using the Amazon Athena connector.

- Step 6: Performed data transformation using Power Query. Observed that the initial rows contained several null values, which affected data alignment. Applied a filter on the ‘Rank’ column to remove null entries, ensuring the dataset starts accurately from Rank 1 for further analysis.
