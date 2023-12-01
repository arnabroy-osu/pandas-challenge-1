# Title
Module 4 Challenge pandas-challenge-1

## Source Data
The source data is provided in the form of a csv file. The file is located in the Resources folder. The file name is `client_dataset.csv`. The file seeems to contain the sales & shipping data for all clients. The data granularity is at the client, Order ID, Item ID & Qty level.

## Initial Preparation exploration
The data is read into a pandas dataframe. We did some initial data exploration, checking for data types and some sanity checks to ensure that the data is clean like existence of null values, check for duplicate records. We also did some data profiling to get some information like which category and sub-category has the highest number of records. We also found the top-5 clients who contributed to this Sales data & stored the respective Client IDs in a list so that we can filter the data for these clients for further analysis. We used the value_counts() function to get the count of records for each client and used tolist() function to convert the series to a list. 

## Data wrangling and transformation
We used the Unit Weight, Price & Quantity to calculate the shipping cost, Line Cost & Line Price using the shipping rule provided in the instruction set and the Sales Tax %. Finally the Profit for eack line item was calculated as the difference between the Line Price & Line Cost. We verified the dollar amount matching the email receipts for 3 orders IDs. We used the Lambda function to apply the shipping rule to calculate the shipping cost. 

## Data Summary & Analysis
The data was then grouped by Client ID to get the total Quantity, total Shipping Price, total revenue & total profit for those top-5 clients and stored the results in a summarized data frame. The data was then sorted in descending order of Total Profit. We used the isin() function to filter the data of the detailed data frame for the top-5 clients which was stored in a list and then used groupby of Client ID with sum() aggregate get the total of Quantity, Shipping Price, Revenue & profit at client ID level. The summarized dollar amounts were then formatted to show the dollar sign with 2 decimal places and in millions. We applied Lambda function and ran it through a FOR loop through a series of Colunmns to achieve this formatting. FOR loop was used to avoid writing the same code for each column.


## Data Analysis Summary & Conclusion
Analyzing the data for top 5 clients with highest number of records , the following observations can be made:
    1. The top 5 clients are: 
        -   1.  Jessica Reyes (Client ID: 33615)
        -   2.  Angela Everett (Client ID: 66037)
        -   3.  Bryan Myers (Client ID: 46820)
        -   4.  Alexandra Young (Client ID: 38378)
        -   5.  Kendra Garrett (Client ID: 24741)

    2. The Total Profit is directly proportional to the Total Revenue. The more the Revenue, the more the profit.

    3. No loss is incurred for any of the top 5 clients.
