# Data Analysis: Power-Outages in California 📊

### February 2023

---

## Introduction

Electricity is indispensable. From the lights in our room and to the screens of our electronic devices, we need electricity.

However, what if we suddenly just lose that power and everything goes dark?
This would be a total nightmare. No lights but only darkness. 

This is why we should study power-outages! 

There are many methods for power-outages, but I will they usually happen due random chance, natural disasters, or human actions.
Random chance and human actions are hard to analyze, especially when finding how power-outages occur because there can be infinite 
number of reasons for a cause of a power-outage. Therefore, I will be analyzing power-outages from natural disasters, particularly severe weather. 

---

## Dataset

**Description:** The dataset used in the analysis comes from the article "A Multi-Hazard Approach to Assess Severe Weather-Induced Major Power Outage Risks in the U.S." The data describes major outages in the states of the U.S. between January 2000 and July 2016. It contains information on major outage patterns and characteristics of each state in the United States, including their climate and topographical characteristics, electricity consumption patterns, population, and land-cover characteristics. With this information, we can study historical trends of major power outages to predict potential outages in the future.

**Rows:** 1534

**Relevant Columns:**

1) POSTAL.CODE - Represents the postal code of the U.S. 

2) CAUSE.CATEGORY - Categories of all the events causing major power outages 

3) CAUSE.CATEGORY.DETAIL - Detailed description of the event categories causing the major power outages

4) TOTAL.SALES - Total electricity consumption in the U.S. state (mw/hr)

5) RES.PERCEN - Percentage of residential electricity consumption compared to the total electricity consumption in the state (in %)

6) COM.PERCEN - Percentage of commercial electricity consumption compared to the total electricity consumption in the state (in %)

7) IND.PERCEN - Percentage of industrial electricity consumption compared to the total electricity consumption in the state (in %)

8) TOTAL.CUSTOMERS - Annual number of total customers served in the U.S. state

9) CLIMATE.CATEGORY - This represents the climate episodes corresponding to the years. The categories—“Warm”, “Cold” or “Normal” episodes of the climate are based on a threshold of ± 0.5 °C for the Oceanic Niño Index (ONI)

---

## Exploratory Data Analysis

### Data Cleaning

The dataset contains many null values and the columns and rows are not a great way for me to extract data. Here is a slice of the raw data:

| Major power outage events in the continental U.S.                                                           | Unnamed: 1   | Unnamed: 2   | Unnamed: 3   |
|:------------------------------------------------------------------------------------------------------------|:-------------|:-------------|:-------------|
| Time period: January 2000 - July 2016                                                                       | nan          | nan          | nan          |
| Regions affected: Outages reported in this data file affected a single U.S. state at the time of occurrence | nan          | nan          | nan          |
| nan                                                                                                         | nan          | nan          | nan          |
| nan                                                                                                         | nan          | nan          | nan          |
| variables                                                                                                   | OBS          | YEAR         | MONTH        |
| Units                                                                                                       | nan          | nan          | nan          |
| nan                                                                                                         | 1            | 2011         | 7            |
| nan                                                                                                         | 2            | 2014         | 5            |
| nan                                                                                                         | 3            | 2010         | 10           |
| nan                                                                                                         | 4            | 

The data is not very organized. The most left column has information such as the general title for the time period and variable//units for columns that I need. In addition, from index 0 to 3 there are extra null rows.

After cleaning the data, I get:

|    |   OBS |   YEAR |   MONTH | U.S._STATE   | POSTAL.CODE   |
|---:|------:|-------:|--------:|:-------------|:--------------|
|  0 |     1 |   2011 |       7 | Minnesota    | MN            |
|  1 |     2 |   2014 |       5 | Minnesota    | MN            |
|  2 |     3 |   2010 |      10 | Minnesota    | MN            |
|  3 |     4 |   2012 |       6 | Minnesota    | MN            |
|  4 |     5 |   2015 |       7 | Minnesota    | MN            |
|  5 |     6 |   2010 |      11 | Minnesota    | MN            |
|  6 |     7 |   2010 |       7 | Minnesota    | MN            |
|  7 |     8 |   2005 |       6 | Minnesota    | MN            |
|  8 |     9 |   2015 |       3 | Minnesota    | MN            |
|  9 |    10 |   2013 |       6 | Minnesota    | MN            |

There are more rows, but I organized everything into its own columns and converted certain values like date and time into datetime objects.

### Visualizations

Since I will be focusing on the severe weather in states, let us take a look at some statistics regarding outages.

<iframe src="assets/state_outages.html" width=800 height=600 frameBorder=0></iframe>


### Statistics of States above 50 Power-Outages 

---

## Missingness



### NMAR in the data



### Total Variation Distance

---

## Does Power-Outages occur mainly because of wildfires in California?



### Hypothesis Test 



### Conclusion




