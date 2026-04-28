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

<img width="868" height="626" alt="Image" src="https://github.com/user-attachments/assets/2fe87a02-e9c2-4f7d-a120-af14ef337587" />



- Step 14:To investigate the source of the problem, I opened the original Excel file and copied the Rank IDs of the error rows, identified via the unique Rank column, into a separate worksheet for further analysis.


<img width="240" height="379" alt="Image" src="https://github.com/user-attachments/assets/b0062ca2-1f8f-4666-8606-cc1804bf97d7" />



- Step 15: To identify and verify the errors, I applied the VLOOKUP function, as illustrated below.


		=VLOOKUP(A2,'Video Games '!$A$1:$D$16578,4,0)


- Step 16: By analyzing the Rank column, I found that the Year column contained missing values, as illustrated below.

- Step 17: Upon reviewing the Year column, I identified errors in the Rank column as well. To verify the Rank values, I applied the VLOOKUP function as illustrated below.

		=VLOOKUP(A2,Sheet1!$A$1:$A$379,1,0)


- Step 18: The errors in the Year column were successfully identified using Excel, and the corrected Year data was then copied into Power Query for further transformation.

- Step 19: In the Year Fixed table, the “N/A” values in the Year column were replaced with 0, and the data type was then changed to Whole Number.

- Step 20: The Year Error Fixed table was combined with the Video Game table using the Append function. Before appending, the data types and column names in the Year Error Fixed table were reviewed to ensure consistency.

- Step 21: In the final table, the null values in the North America Sales column were replaced with 0.
  

<img width="995" height="426" alt="Image" src="https://github.com/user-attachments/assets/758fd9d5-a8e4-4229-bff2-df6667b676ad" />


- Step 22: In the Sales columns, all decimal values were converted into millions by multiplying them by 1,000,000.


<img width="396" height="312" alt="Image" src="https://github.com/user-attachments/assets/f7bc7a66-23ae-4c24-8870-33108fdba0d7" />

<img width="698" height="220" alt="Image" src="https://github.com/user-attachments/assets/593df5b2-ec65-40b8-86db-1411054ef827" />


- Step 23: Created the first report view page and imported a radar chart visual using a Power BI Service account to access additional custom visuals.

- Step 24: Configured a radar chart by assigning the Genre column to the Category field and mapping North America sales to the Y-axis in the visualization pane.

- Step 25: Built and overlaid radar chart visuals for Europe, Japan, Other, and Global regions to support multi-region comparison within a single view.

- Step 26:Implemented bookmarks for multiple regional views and leveraged the Selection Pane to control visual visibility, enabling seamless interactive navigation across regions.

- Step 27: Configured Bookmark Navigator buttons to provide interactive and efficient navigation between multiple visual states within the report.

 # Report Snapshot (Power BI DESKTOP)

 <img width="924" height="486" alt="Image" src="https://github.com/user-attachments/assets/c3df245d-0121-4aa6-9848-046c5045b41d" />
<img width="920" height="482" alt="Image" src="https://github.com/user-attachments/assets/8eb75adc-7dd6-44cb-84c3-861bfff9174f" />
<img width="916" height="491" alt="Image" src="https://github.com/user-attachments/assets/037a1a2e-8fbc-432b-87f2-48f74dd5b71b" />
<img width="923" height="499" alt="Image" src="https://github.com/user-attachments/assets/835e1809-6e8f-47e5-9811-02702201a878" />
<img width="896" height="491" alt="Image" src="https://github.com/user-attachments/assets/e752f131-6d58-407d-8af4-0c7b6d44f1fc" />


- Step 28: Developed a radar chart using slicers as an alternative approach to analyze and compare sales values across different regions, including North America, Japan, Europe, Other Regions, and Global.

- Step 29: As part of the second approach, duplicated the original dataset in Power Query to support alternative analysis and visualization.

- Step 30: Selected all five regional columns and applied the Unpivot function in Power Query, resulting in two columns: Attribute and Sales Value.

<img width="831" height="526" alt="Image" src="https://github.com/user-attachments/assets/94139355-8183-4d6a-a0ff-b00740c63d6e" />

<img width="743" height="524" alt="Image" src="https://github.com/user-attachments/assets/78dc3e6c-72ad-404a-89c3-e687517d8a0e" />

- Step 31: Designed a secondary report page (‘Approach 2’) with a consistent canvas theme and implemented a radar chart to analyze genre-based sales performance.

- Step 32: The second report view demonstrates that the desired output was successfully replicated using slicer-based interactions.

<img width="915" height="482" alt="Image" src="https://github.com/user-attachments/assets/03b6191e-2a20-4252-bdc8-ade1c510330a" />

- Step 33: Developed a third report page featuring a matrix visual to analyze and present sales performance by genre and year across all regions.

- Step 34: Added page navigator buttons on Report Pages 1 and 2 to enable easy navigation to the matrix visual on Page 3.

- Step 35: Implemented a back-navigation button on Page 3 to enable seamless return to the radar chart view.


