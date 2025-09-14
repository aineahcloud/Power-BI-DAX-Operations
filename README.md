# Power BI Mini-Projects: DAX measures for visualisation Power Bi
This project demonstrates a series of data analysis techniques and visualizations using a sample sales dataset in Power BI. The goal was to transform raw data into a set of actionable insights through the use of DAX formulas, dynamic reporting, and effective data presentation.

## Project Highlights
This project showcases a range of Power BI skills, including:

### DAX Calculations: 
Creating measures for key business metrics such as Year-to-Date (YTD) Sales and percentage of total sales.

### Dynamic Visualizations: 
Building a chart with a dynamic title that changes based on a slicer selection, and creating a report that shows the top N products in each category.

### Data Formatting: 
Applying conditional formatting to highlight important data points and logically sorting charts (e.g., sorting age groups in a specific order).

### Key Performance Indicators (KPIs): 
Developing a KPI to track and visualize sales performance over the last three months.

## Key DAX Formulas Used
Here are some of the core DAX formulas implemented in this project:

### Year-to-Date (YTD) Sales
The TOTALYTD function was used to calculate the cumulative sales from the beginning of the year up to the current date.

 Total YTD Sales = TOTALYTD(SUM('Sales'[Total Sales]), 'Dates'[Date])

### Percentage of Total Sales
This formula calculates each category's contribution to the overall sales. The ALL function removes any filters on the category column to get the total sales for the entire dataset.

Percent of Total Sales =
DIVIDE(
    SUM('Sales'[Total Sales]),
    CALCULATE(
        SUM('Sales'[Total Sales]),
        ALL('Product'[category])
    )
)

### Last 3 Months' Sales
The DATESINPERIOD function was used to calculate the sum of sales for the most recent three months, providing a clear and concise view of recent performance.

Last 3 Month Sales =
CALCULATE(
    SUM('Sales'[Total Sales]),
    DATESINPERIOD(
        'Dates'[Date],
        LASTDATE('Dates'[Date]),
        -3,
        MONTH
    )
)

How to Get Started
To explore this project, you can open the .pbix file in Power BI Desktop. You will need to have Power BI Desktop installed on your computer.

Feel free to download and use this project as a reference for your own work.
