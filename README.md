# Canadian Immigration Data Analysis (1990 - 2013)

# Table of Contents
1. [Overview](#overview)
2. [Dataset](#dataset)
3. [Tools](#tools)
4. [Data Preparation](#data-preparation)
5. [Visualization](#visualization)
   - [Trends Over the Years](#trends-over-the-years)
   - [Top and Least Contributing Countries](#top-and-least-contributing-countries)
   - [Heatmap of Immigration Density](#heatmap-of-immigration-density)
   - [Developed vs Developing Regions](#developed-vs-developing-regions)
   - [Top Countries With Significant Increase In Immigration](#top-countries-with-significant-increase-in-immigration)
   - [Case Study: Immigration from Haiti](#case-study-immigration-from-haiti)
6. [Interactive Dashboard](#interactive-dashboard)
7. [Conclusions](#conclusions)

## Overview
This project explores immigration data to Canada from 1990 to 2013, with a focus on discovering trends, patterns, and insights using Python's data analysis and visualization libraries.

## Dataset
The dataset contains detailed records of immigrants from different countries and regions to Canada, with attributes such as country of origin, number of immigrants per year, and classification by developmental status of the originating country.

## Tools
- **Python**: The core language used for the analysis.
- **Pandas**: Employed for efficient data manipulation and cleaning.
- **Matplotlib & Seaborn**: Utilized for generating insightful visualizations.
- **Jupyter Notebook**: Served as an interactive computational environment for coding and presenting the analysis.

## Data Preparation
Data preparation involved several steps to ensure data quality and readiness for analysis:
- Reading data from the source Excel file.
- Cleaning irrelevant columns and rows.
- Renaming columns for better clarity and consistency.
- Setting appropriate indices for easier data manipulation.

```python
df_can.drop(['AREA', 'REG', 'DEV', 'Type', 'Coverage'], axis=1, inplace=True)
df_can.rename(columns={'OdName':'Country', 'AreaName':'Continent','RegName':'Region'}, inplace=True)
df_can.set_index('Country', inplace=True)
```

## Visualization
I created multiple visualizations to extract and present the story behind the data:

### Trends Over the Years
Line plots were used to visualize the immigration trends from various countries across the years.

### Top and Least Contributing Countries
- Identification of the top 5 countries with the highest number of immigrants.
- Analysis of the least 5 countries contributing to immigration.

![Top 5 Countries](/images/top5_trend.jpg)
This shows that UK had a spike in immigrations to Canada during 1994 and 1995, followed by a steep decline. Furthermore, both China and India follow a very similar increasing trend, with a peak in 2005.
![Least 5 Countries](/images/least5_trend.jpg)

### Heatmap of Immigration Density
A heatmap was generated to visualize the density of immigration across different countries over the years, providing a color-coded representation of the data.

![Heatmap](/images/immigration_density.jpg)

### Developed vs Developing Regions
Comparison of immigration trends between developed and developing regions, highlighting the disparities and trends over the decades.

![Developed vs Developing](/images/developed_vs_developing_regions.jpg)
Expectedly, developing regions have a much higher immigration trend to Canada than that of developed regions.

### Top Countries With Significant Increase In Immigration
We need to define a threshold for significant increase and identify countries with changes beyond this threshold. This can be done by calculating the annual change for each country over the entire period and the mean annual change and standard deviation of these changes. From these statistics, we can define a threshold. 
![Significant Increase](/images/top5_significant_increase.jpg)

### Case Study: Immigration from Haiti
In 2010, Haiti suffered a catastrophic magnitude 7.0 earthquake. The quake caused widespread devastation and loss of life and about three million people were affected by this natural disaster. As part of Canada's humanitarian effort, the Government of Canada stepped up its effort in accepting refugees from Haiti.

I plotted a line chart showcasing the significant spike in Haitian immigration to Canada following the 2010 earthquake, illustrating Canada's humanitarian response.

![Immigration from Haiti](/images/haiti_immigration.jpg)

## Interactive Dashboard
I built an interactive dashboard to allow users to dynamically explore the immigration data by continent, region, and country, facilitating a deeper understanding through user interaction.
We can drill down from Continents to Regions and then to Countries by clicking on the bars.
![Interactive Dashboard](/images/interactive1.jpg)
![Interactive Dashboard](/images/interactive2.jpg)
The **Go Back** button brings out the roll back functionalities, allowing us to go from Country to Region and then to Continent again.
![Interactive Dashboard](/images/interactive3.jpg)

## Conclusions
My analysis unearthed various trends, such as the impact of global events on immigration and the variations in immigration patterns by economic status of countries. The visualizations made it possible to quickly identify these trends and draw meaningful insights.
