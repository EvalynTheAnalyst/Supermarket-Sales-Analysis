# Supermarket Sales Dashboard

This project features an interactive Excel dashboard developed to analyze supermarket sales data in Kenya.


<img width="775" alt="image" src="https://github.com/user-attachments/assets/d2b2ed74-2536-4c5a-a5a9-3e959da391f6">




## Data Source
The data used in this project is [here](https://github.com/nyarotoyi/excel-portfolio/blob/main/Supermarket-Sales-Dashboard/assignment.xlsx).

## Project Overview
The goal of this project is to analyze the supermarket sales dataset to derive actionable insights related to consumer behavior, sales performance per supermarket chain, category, and location, peak selling hours and days, product placement, and targeted promotions.


## Features
- **Supermarket Sales Analysis**: Visualizes total sales by each supermarket.
- **Sales by Payment Type**: Displays the distribution of sales by payment method (cash or card).
- **Sales by Time of Day**: Shows trends in sales throughout different times of the day.
- **Sales by Day of Week**: Analyzes sales performance on different days of the week.
- **Location Analysis**: Provides insights into sales based on different locations.

# The Analysis

## 1. Data Preparation

**Data Import**
  
- Open the file in Excel.
- Copy all the content and paste to a new worksheet named Backup and name the working worksheet Dataset
- Convert the data range to a Table using `ctrl + T` , ensure you check on `My table has headers`
  
**Data Cleaning**
- *Remove duplicates:* For our data, there is no unique identifier so you will ignore this part, however to remove duplicates in case of Unique ID select the Data Ribbon > Under Data Tools select Remove Duplicates > Select Unique ID colum and click ok.

- *Check for empty cells:*  You check if there are empty cells by using

`=ISBLANK(range)` i.e `ISBLANK(Table1)` - This will return `FALSE` if there's no missing values and `TRUE` if there are empty cells.

The other option is to check the total number of empty cells using:

`=SUMPRODUCT(--(ISBLANK(Table1)))`  -- Ensure you confirm ther range

- *Format the data*
  
      - Ensure all columns are properly formatted (e.g., dates as Date format, numbers as Number format).
  
      - Remove any unnecessary spaces or errors in the data.
  
For our case the original date format was not in the proper date format- We split the date columns using the Text to column data tool in the Data Ribbon, then connected the dates back in the right format using `DATE()` Function.

# 2. Exploratory Data Analysis (EDA)

### 1. **Data Overview**
*Dataset Description* Provide a brief description of the dataset, including the number of records and columns.
The data contains 1229 records(rows) and 19 features(columns) (Before we create the new calculated columns)
*Columns*
 - Supermarket: Name of the supermarket chain
 - No_of_Items: Number of items purchased in each transaction
 - Variation: Number of item variations purchased
 - Total_Paid: Total amount paid for the transaction
 - Type: Payment type (e.g., cash, card, mpesa)
 - Food, Snack, Beverage, Consumables, High_End, Asset, Fixed_Asset: Boolean indicators for purchased item types
 - Date: Date of the transaction
 - Time: Time of the transaction
 - Type_Market: Type of market (e.g., chain, small)
 - Mall: Whether it’s located in a mall or not
 - Location: Specific location of the supermarket
 - Location_Category: Location category (e.g., high, mid, low)
 - Day: Day of the week

Explore the dataset content by filtering through the filters drop down on the column headers.

Freeze the header row- First delete the content in the top 3 rows to ensure the header row comes first, then freexe it by ging to the View Ribbon > in the Window group select `Freeze Panes` drop down and Select `Freeze Top Row`

In the `Table Design` Ribbon check Total Row (Its in the Table Style Option group)

This will introduce a new row at the end of the dataset that allows us to perform basic statistical summaries to our data

![TotalRow](https://github.com/nyarotoyi/excel-portfolio/blob/main/Supermarket-Sales-Dashboard/totalrow.jpg)

**Initial Insights**

   - *Sales Trends:* Highlight any initial insights or trends observed in the data.
     - More sales were made in 2017 (2456706) than 2016 (22176) This is a huge margin that probably alludes to the fact that our dataset could be  having incomplete and might not reflect the actual market sales volume, However since this is for learning purposes, we will continue with the analysis.
  
     - Most supermakets have one entry record. Kassmart has more entries at 365 followed by Tumaini at 268
       
   - *Geographical Insights*
     Supermarkets located in the mid categories are more and have higher sales(1581322) followed by the chains(794692)
## Calculated Columns
We Create additional columns (features) from existing ones that could aid in the analysis.
The features are Day Type (weekend or weekday), Time of Day (morning, afternoon, evening). Find the Formulas used in the `Useful formulas ` worksheet 

# 3 Analysis
Insert Pivot tables by selecting Insert > Pivot table and selecting where you want it placed

Select the field(colunm name) you want to calculate and dug it to the areas below the field names, i.e values for summary calculations, columns or rows.

- **PivotTables:**
  - Total Sales by Supermarket
  - Sales by Location
  - Sales per Year
  - Sales by Payment Type
  - Sales  by Day of week
  - Sales by Time of day
  
- **Charts:** This are the choice of charts for visualization
  - Total Sales by Supermarket - Column chart
  - Sales by Location - Column chart
  - Sales per Year - dougnut chart
  - Sales by Payment Type - column chart
  - Sales  by Day of week- doughnut chart
  - Sales by Time of day -   3-D clustured column chart

# 4. Dashboard

The dashboard serves as the central hub for analyzing supermarket sales data. It integrates key metrics and visualizations from various worksheets into a cohesive view.

**Dashboard Layout**

**Main View**
- The dashboard is set up as the "Home" worksheet, which consolidates information from the Sales Performance, Customer Behavior, Useful Formulas, and Dataset worksheets.
- *Charts and Visualizations* Charts and graphs from other worksheets have been copied to the dashboard and organized to highlight important trends and metrics.
- 
**Navigation**

- Navigation Icons Icons are included on the dashboard to enable quick access to different sections of the workbook. These sections include:
    - Sales Performance Worksheet: Detailed sales performance analysis.
    - Customer Behavior Worksheet: Insights into customer behavior patterns.
    - Useful Formulas Worksheet: List and explanation of useful formulas.
    - Dataset Worksheet: Raw data used for analysis.
      
** Linking Navigation Icons**

Step-by-Step Instructions:

- Insert Icons:
Go to the dashboard worksheet.

Use Insert > Shapes or Insert > Icons to add visual elements that will serve as navigation buttons.

- Add Hyperlinks:

Right-click on the icon and select "Link" or "Hyperlink."

In the "Insert Hyperlink" dialog box, choose "Place in This Document."

Select the target worksheet from the list (e.g., Sales Performance).

Click "OK" to create the link.

- Test Links:
Click on the icons to ensure they navigate to the correct worksheets.

**Interactive Elements**

Slicers*

- Location Slicer: Added to the Sales Performance worksheet, allowing users to filter data by location. The slicer is linked to all relevant PivotTables in the workbook for synchronized filtering.

Linking Slicers:

Right-click the slicer and choose "Report Connections" (or "PivotTable Connections").
Check all PivotTables that should be controlled by the slicer.
Copy the slicer to the dashboard for comprehensive filtering across visualizations.

**Design Considerations**

Visual Design**

- Consistency: Consistent colors and fonts are used throughout to maintain a unified look and feel.
- Clarity: Charts and visualizations are clearly labeled and formatted to highlight key insights.
- Usability: The layout is intuitive, with interactive elements easily accessible. Navigation icons facilitate quick transitions between sections.
Impact on Usability:

The dashboard enhances usability by consolidating data into a central view. Interactive elements such as slicers allow for dynamic data exploration. The clear layout and functional navigation improve user experience and efficiency.

## Conclusion

The analysis of the supermarket sales data in Kenya provides valuable insights into sales performance, consumer behavior, and operational trends. The interactive dashboard effectively consolidates key metrics, allowing for dynamic data exploration and easy access to detailed reports.

### Key Findings

1. **Sales Performance:**
   - **Top Performing Supermarkets:**
     - **Naivas** leads in revenue, followed by **Quickmart** and **Tumaini**. These supermarkets have consistently higher sales figures.
   - **Bottom Performing Supermarkets:**
     - **Kassmart**, **Selfridges**, and **Fairways** rank lowest in sales. Notably, Kassmart's high entry count suggests it might be focused on lower-priced items.
   - **Top Selling Locations:**
     - The **CBD** area generates the highest sales, with **Ongata Rongai** and **Kilimani** following.

2. **Customer Behavior:**
   - **Day of the Week:**
     - Sales are generally higher on weekdays compared to weekends. This indicates a stronger consumer purchasing trend during the workweek.
   - **Payment Types:**
     - Cash is the most common payment method, with cards and M-Pesa following. This suggests that while digital payments are used, cash remains dominant.
   - **Time of Day:**
     - Sales peak in the afternoon and are slightly higher in the evening than in the morning. This information can be used for optimizing store hours and staffing.

### Recommendations

1. **Focus on High-Performing Supermarkets:**
   - Invest in strategies and marketing campaigns similar to those used by top-performing supermarkets like Naivas and Quickmart to boost sales in other branches.

2. **Optimize Inventory and Pricing:**
   - For supermarkets with lower sales, consider reviewing inventory and pricing strategies. The high number of entries for Kassmart could indicate a need to assess its pricing and product mix.

3. **Leverage Location Data:**
   - Target promotions and marketing efforts in high-performing locations such as CBD, Ongata Rongai, and Kilimani. Explore opportunities to expand or enhance offerings in these areas.

4. **Adjust Payment Options and Store Hours:**
   - Enhance digital payment options and consider extending store hours during peak times in the afternoon and evening to capture more sales.

### How to Use

1. **Download the Excel File:**
   - Access the file from this repository [here](https://github.com/nyarotoyi/excel-portfolio/blob/main/Supermarket-Sales-Dashboard/assignment.xlsx).
   
2. **Open the File:**
   - Open the file in Microsoft Excel to view the interactive dashboard and detailed analysis.

3. **Use Interactive Features:**
   - Utilize the slicers to filter data and explore different aspects of the sales performance.


## Requirements
- Microsoft Excel 2016 or later.

## Contact Me

Email- zianaodero@gmail.com

[LINKEDIN](https://www.linkedin.com/in/marice-ziana-a51442146/)

