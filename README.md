
# Sales Report

## Problem Statement

The goal is to assemble a sales dashboard with different visuals to show key sales insights like total revenue, cost, profit, growth rates etc. using the sales data available in different files and tables. The data needs to be loaded, transformed and modeled to connect various dimension tables for analysis using Power BI. Various calculations also need to be created using DAX to derive the required measures.

### Steps followed

- Step 1 : In the report view, under the insert tab, one text boxes were added to the canvas, in this name of the report was mentioned that is "Sales Report".
- Step 2 : Load data into Power BI Desktop, dataset is a csv file.
- Step 3 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" options.
- Step 4 : Visual filters (Slicers) were added for three fields named "Country", "Year", "Month Name".
- Step 5 : Three card visuals were added to the canvas, one representing total revenue, second representing Gross Profit & Third representing Sum of Units.
   - New Measure was created to find Total Revenue.

      Following DAX expression was written for the same,
   
         "Total Revenue = Sales[Units] * RELATED('Product'[RetailPrice])"

     A card visual was used to represent this Total Revenue.

     Snap of Total revenue. 

     <img width="72" alt="Total Revenue" src="https://github.com/Kushalwadatkar/Sales_Report_Project/assets/96763572/15e50005-7169-493e-b974-bfdb95f693b2">


   - New Measure was created to find Gross Profit.

     Following DAX expression was written for the same,
      
         "Gross Profit = Sales[Total Revenue] - Sales[Total Cost]"
   
      A card visual was used to represent this Gross Profit.
   
      Snap of Gross Profit.
   
      <img width="70" alt="Gross Profit" src="https://github.com/Kushalwadatkar/Sales_Report_Project/assets/96763572/64a560fe-cdcc-4775-81f0-e9b3a216c4d0">

   Using visual level filter from the filters pane, basic filtering was used & null values were unselected for consideration into calculation.
- Step 6 : A multi-row card chart was also added to the report design area representing the Top 5 Sales persons filtering by Gross Profit.
- Step 7 :A table was added to report design area in this two columns were present, one  representing the date & other one representing the average of total revenue & Applied conditional formatting to both columns.
- Step 8 : A stacked column chart was added to report design area representing the total revenue by product name & Sub Category key. While creating the visual, field named "Sub category key" also added to the Legends bucket.
- Step 9 : A Pie chart was added to the report design area representing the gross profit by sub category name. Sub category names were extra, super,micro,regular. 
- Step 10 : A waterfall chart was added to report design area representing the total revenue & units by year & product name. While the visualing, field named "Year" added to the Category bucket, "ProductName " added to the breakdown bucket, "Total Revenue" added to the Y-axis & "Units" added to the tooltips.
- Step 11 : A line chart added to the report design area representing the total revenue & QoQ Growth by Quarter (QoQ Growth represent Quarter-on-Quarter Growth). 
   - New Measure was created to find Quarter-on-Quarter Growth.

     Following DAX expression was written for the same,

         "QoQ Growth = ([Total Rev]-[Prev Qtr]) / [Prev Qtr]"
- Step 12 : A another Line chart was added to the report design area representing the Gross profit & MoM Growth by Month Name (MoM Growth represent Month-on-Month Growth).
   - New Measure was created to find Month-on-Month Growth
     
      Following DAX expression was written for the same,

         "MoM Growth = ([Total Profit]-[Prev Month Profit]) / [Prev Month Profit]"

- Step 13 : The report was then published to Power BI Service.

   ![Publish Message](https://github.com/Kushalwadatkar/Sales_Report_Project/assets/96763572/7caf52b0-9eaa-4953-8ea4-0afdaf7f4682)

# Snapshot of Dashboard (Power BI Service)
   ![Report Upload Service](https://github.com/Kushalwadatkar/Sales_Report_Project/assets/96763572/adf75abf-082c-4a74-9647-e92f27431afa)

# Snapshot of Report (Power BI DESKTOP)
   ![Dasboard Desktop](https://github.com/Kushalwadatkar/Sales_Report_Project/assets/96763572/35b5fe06-0483-4fe9-aa73-f05bcc88a264)

# Insights

- Data is provided in different files/formats for sales (by year), categories, geography, products, and sales reps.
- Tasks involve loading all sales files into a single fact table, transforming location data, cleaning IDs, and building the data model connecting all tables.
- DAX calculations need to be created for total revenue, total cost, gross profit, month-over-month profit growth, average daily sales, and breakdown/trend analysis by product.
- Data is categorized and aggregated by dimensions like country, year, month, product, sub-category etc. This allows for detailed analysis across various levels.
- Revenue and growth figures are given by quarter. Gross profit and month-on-month growth is shown by month.
- It provides monthly, quarterly and yearly sales figures. There are also comparisons between years.
- The overall goal is to analyze and visualize the provided sales data in a clear and insightful one-page dashboard using various visuals and DAX calculations, with creativity in the visualization approach encouraged.

