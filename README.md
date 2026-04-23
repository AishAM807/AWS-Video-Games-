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

 Step 7: Collected additional data using a CSV file.


- Step 8: The second table contains 21 rows and the same number of columns as the first table.

- Step 9: Before appending these two tables, I ensured that the column names and data types matched across both tables. Then, I combined them into a single table.

- Step 10: I encountered an error while converting the Year column from text to date data type.

- Step 11: I created a duplicate dataset to troubleshoot and resolve data type errors in the Year column.

- Step 12: Within the duplicate dataset, I changed the Year column to a whole number format to detect rows causing errors.

- Step 13: By applying the Keep Rows function and leveraging column profiling, I segregated error rows and found exactly 378 errors in the Year column.

- Step 14:To investigate the source of the problem, I opened the original Excel file and copied the Rank IDs of the error rows, identified via the unique Rank column, into a separate worksheet for further analysis.

- Step 15: To identify and verify the errors, I applied the VLOOKUP function, as illustrated below.


		=VLOOKUP(A2,'Video Games '!$A$1:$D$16578,4,0)


- Step 16: By analyzing the Rank column, I found that the Year column contained missing values, as illustrated below.

- Step 17: Upon reviewing the Year column, I identified errors in the Rank column as well. To verify the Rank values, I applied the VLOOKUP function as illustrated below.

		=VLOOKUP(A2,Sheet1!$A$1:$A$379,1,0)


- Step 18: The errors in the Year column were successfully identified using Excel, and the corrected Year data was then copied into Power Query for further transformation.

- Step 19: In the Year Fixed table, the “N/A” values in the Year column were replaced with 0, and the data type was then changed to Whole Number.

- Step 20: The Year Error Fixed table was combined with the Video Game table using the Append function. Before appending, the data types and column names in the Year Error Fixed table were reviewed to ensure consistency.

- Step 21: In the final table, the null values in the North America Sales column were replaced with 0.

- Step 22: In the Sales columns, all decimal values were converted into millions by multiplying them by 1,000,000.

