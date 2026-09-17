
# UPI Transaction-Report
##  Power BI Report

The complete Power BI report is available as a `.pbix` file.

**[Download Power BI Report](UPI%20Transaction%20Analysis.pbix)**

> Open the `.pbix` file using Power BI Desktop to see interactive dashboard.



## Problem Statement

This Power BI dashboard analyzes UPI transactions for 2024 to identify transaction trends, customer behavior, and payment patterns. It provides insights based on monthly transaction activity, geographical performance, banks, payment methods, devices, merchants, purposes, and customer demographics along with their account balance analysis. 

The dashboard enables businesses to compare transaction performance across different cities and customer segments, helping them understand UPI usage patterns and make data-driven decisions.


### Steps followed 

- Step 1 : Loaded data into Power BI Desktop, dataset was in excel file.
- Step 2 : Transformed data into Power Query Editor for cleaning and basic analysis purpose such as "column distribution", "column quality" and "column profile".
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : I observed that none of the columns have errors or empty values but i converted 'CustomerAccountNumber' and 'MerchantAccountNumber' from Whole Number to Text data type to display the complete account numbers and avoid scientific notation.
- Step 5 : Clicked "Close & Apply", it redirected to the power BI report view.
- Step 6 : In the report view, under Visualizations pane, I added 10 slicers to allow users to interactively filter the dashboard. I standardized their size and spacing and aligned them properly using the General ->  properties in the Visualizations pane, making the dashboard look clean, organized, and easy to use.
- Step 7 : Created a new column called Age Groups in the Transaction Details table using DAX to categorize customers into three age groups [A1,A2,A3]. This column was then added to a slicer.

for creating new Age Groups column following DAX expression was written:
       
       
        
    Age Groups = IF('Transaction Details'[CustomerAge]<=30,"A1 [20-30]",
		         IF('Transaction Details'[CustomerAge]<=45,"A2 [31-45]",
		         "A3 [46-59]"))
        
Snap of new calculated column ,

![Age Groups calculated column](https://raw.githubusercontent.com/sumanthshetty321/UPI-Transactions-Power-BI-Analysis/main/screenshots/age-groups-calculated-column.png)



- Step 8 : I added columns such as BankNameSent, BankNameReceived, Currency, Gender, PaymentMethod, DeviceType, MerchantName, Status, Purpose, and Age Groups to 10 different slicers.
- Step 9 :I right-clicked on page 1 and selected 'duplicate' option to create a copy of page1 having 10 slicers and renamed it as "copy of page 1"
- Step 10 :In Page 1, I added a line chart to analyze the monthly transaction trend.I placed the 'TransactionDate' field (showing only the month) on the X-axis and Transactions on the Y-axis.

 
- Step 11 :In the Format Visual pane, I customized the line chart by naming it “Transactions by Month(Line)[2024]”. I also changed the line color, enabled data labels and markers, and adjusted the font style and font size to improve the chart’s readability



- Step 12 : In the copy Page 1, I added a "Matrix" visual and I placed 'TransactionDate(Month)' in the Rows, 'City' and 'Currency' in the Columns, and 'Transaction' and 'Balance' in the Values section to compare transaction activity and account balances across different months, cities, and currencies.
- Step 13 : I selected the 'Expand all down one level in the hierarchy' option in the Matrix visual to expand the hierarchy and display all the information together for easier analysis.

- Step 14 :I customized the Matrix visual using the Format Visual pane to improve its appearance, readability, and overall presentation, making the information easier to understand.

        
- Step 15 : I added 'Transactiontype' column to filters on all pages in 'Filters' pane so that users can filter the entire dashboard based on transaction type.

        
 - Step 16 :I connected the slicers across both pages using 'View' → 'Sync slicers'. I enabled each slicer for both pages so that the selected filters remain synchronized and apply consistently across the entire dashboard.
 

 
 Snap of Sync slicers:
 
 ![Sync Slicers](https://raw.githubusercontent.com/sumanthshetty321/UPI-Transactions-Power-BI-Analysis/main/screenshots/Sync%20slicers.png)
 
 - Step 17 : In Page 1, I copied the 'Transaction by month' line chart, converted the copy into a 'bar chart' and pasted it on top of the original chart,then I created another line chart and bar chart to analyze 'Balance by month' and placed all four charts on top of each other so that they could be switched using bookmarks.

 Snap of Selection and Bookmarks pane:

 ![Selection and Bookmarks pane](https://raw.githubusercontent.com/sumanthshetty321/UPI-Transactions-Power-BI-Analysis/main/screenshots/Selection%20and%20Bookmarks%20pane.png) 
 

 - Step 18 : I added a Bookmark Navigator using Insert → Buttons → Navigator → Bookmark Navigator. This created navigation buttons that allow users to switch between the different chart views. I also ensured that the Bookmark Navigator was placed at the top of the Selection pane so it remained visible and accessible.
 
![Bookmark Navigator](https://raw.githubusercontent.com/sumanthshetty321/UPI-Transactions-Power-BI-Analysis/main/screenshots/Bookmark%20navigator.png)
 
.

# Snapshot of Dashboard (Power BI Service)

![dashboard_snapo](https://user-images.githubusercontent.com/102996550/174096257-11f1aae5-203d-44fc-bfca-25d37faf3237.jpg)

 
 # Report Snapshot (Power BI DESKTOP)
Transaction line chart by month[2024]:
![Transaction Line Chart](https://raw.githubusercontent.com/sumanthshetty321/UPI-Transactions-Power-BI-Analysis/main/screenshots/Transaction%20line%20chart.png)


Transaction bar chart by month[2024]:

![Transaction Bar Chart](https://raw.githubusercontent.com/sumanthshetty321/UPI-Transactions-Power-BI-Analysis/main/screenshots/Transaction%20bar%20chart.png)

Balance line chart by month[2024]:

![Balance Line Chart](https://raw.githubusercontent.com/sumanthshetty321/UPI-Transactions-Power-BI-Analysis/main/screenshots/Balance%20line%20chart.png)

Balance bar chart by month[2024]:

![Balance Bar Chart](https://raw.githubusercontent.com/sumanthshetty321/UPI-Transactions-Power-BI-Analysis/main/screenshots/Balance%20bar%20chart.png)

Transaction and Balance Matrix Visual of City and Currency for different months[2024]:
![Matrix Visual](https://raw.githubusercontent.com/sumanthshetty321/UPI-Transactions-Power-BI-Analysis/main/screenshots/Matrix%20Visual.png)
 


# Key Insights



### [1] Monthly Transactions Analysis


Total Number of Transactions in 2024 = 19,874K (19.874M)

Transactions in January = 1,679K (8.45%)

Transactions in February = 1,693K (8.52%)

Transactions in March = 1,624K (8.17%)

Transactions in April = 1,663K (8.37%)

Transactions in May = 1,707K (8.59%)

Transactions in June = 1,653K (8.32%)

Transactions in July = 1,610K (8.10%)

Transactions in August = 1,599K (8.05%)

Transactions in September = 1,667K (8.39%)

Transactions in October = 1,691K (8.51%)

Transactions in November = 1,642K (8.26%)

Transactions in December = 1,646K (8.28%)

Thus, May recorded the highest number of transactions 1,707K (8.59%), while August recorded the lowest 1,599K (8.05%).

### [2] Monthly Balance Analysis


Total Balance across all months in 2024= 100,411K

January Balance = 8,232K (8.20%)

February Balance = 8,353K (8.32%)

March Balance = 8,252K (8.22%)

April Balance = 8,442K (8.41%)

May Balance = 8,222K (8.19%)

June Balance = 8,536K (8.50%)

July Balance = 8,331K (8.30%)

August Balance = 8,433K (8.40%)

September Balance = 8,433K (8.40%)

October Balance = 8,421K (8.39%)

November Balance = 8,327K (8.29%)

December Balance = 8,429K (8.39%)

Thus, June recorded the highest monthly balance of 8,536K (8.50%), while May recorded the lowest monthly balance of 8,222K (8.19%).
  
  
### [3] Bank-wise Transaction Analysis
Axis Bank:

Total Axis Bank Transactions = 4.908M (24.70%)

April Transactions = 1.663M (8.37%)

August Transactions = 1.599M (8.05%)

December Transactions = 1.646M (8.28%)


HDFC Bank:

Total HDFC Bank Transactions = 5.053M (25.43%)

January Transactions = 1.679M (8.45%)

May Transactions = 1.707M (8.59%)

September Transactions = 1.667M (8.39%)


ICICI Bank:

Total ICICI Bank Transactions = 4.876M (24.53%)

March Transactions = 1.624M (8.17%)

July Transactions = 1.610M (8.10%)

November Transactions = 1.642M (8.26%)


SBI Bank:

Total SBI Bank Transactions = 5.037M (25.34%)

February Transactions = 1.693M (8.52%)

June Transactions = 1.653M (8.32%)

October Transactions = 1.691M (8.51%)


Overall Bank Insight:

HDFC Bank = 5.053M (25.43%)

SBI Bank = 5.037M (25.34%)

Axis Bank = 4.908M (24.70%)

ICICI Bank = 4.876M (24.53%)

    Thus, HDFC Bank had the highest transactions among the four banks, while ICICI Bank had the lowest.

### [4] Payment Method

Total Number of Transactions = 19,874K

Phone Number Transactions = 6,641K (33.41%)

QR Code Transactions = 6,590K (33.14%)

UPI ID Transactions = 6,643K (33.43%)

    Thus, UPI ID recorded the highest share of transactions

 
 ### [5] Status
 
Successful Transactions = 15,875K (79.85%)

Failed Transactions = 3,996K (20.11%)
        
    Thus, the majority of transactions were completed successfully.
         
### [6] Gender-wise Analysis
Transactions:

Total Number of Transactions = 19,874K

Female Transactions = 9,945K (50.04%)

Male Transactions = 9,929K (49.96%)


Balance:

Total Balance = 100,411K

Female Customer Balance = 50,614K (50.41%)

Male Customer Balance = 49,797K (49.59%)


    Female customers accounted for 50.04% of transactions and 50.41% of the total balance.

    Male customers accounted for 49.96% of transactions and 49.59% of the total balance.
 
