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

---
In this visual, I look at the count of outages per state.

<iframe src="assets/state_outages.html" width=600 height=600 frameBorder=0></iframe>

---
In addition, I look at the count of outages for each cause.

<iframe src="assets/outages_cause.html" width=600 height=600 frameBorder=0></iframe>

---
Since the focus is on severe weather, here is the amount of outages per type of weather.

<iframe src="assets/outages_weather.html" width=600 height=600 frameBorder=0></iframe>

--- 


Alongside severe weather, I explored the residential, commercial, and industrial electricty consumption rate for each state.

### **Residential Electricity Consumption Rate (%)**

<iframe src="assets/rec_chloro.html" width=600 height=600 frameBorder=0></iframe>

---

 ### **Commercial Electricity Consumption Rate (%)**

<iframe src="assets/cec_chloro.html" width=600 height=600 frameBorder=0></iframe>

---

 ### **Industrial Electricity Consumption Rate (%)**

<iframe src="assets/iec_chloro.html" width=600 height=600 frameBorder=0></iframe>

---

For the states - California, Texas, and Washington - that have over 50 major power-outages, I decided to focus on these states.
I wanted to explore a couple factors outside of severe weather, which included the amount of customers using electricity for these states

### **Total Amount of Customers Affected**

<iframe src="assets/customers_outage.html" width=600 height=600 frameBorder=0></iframe>


### **Total Electricity Consumption (megawatt-hour)**

<iframe src="assets/total_elec_consum.html" width=600 height=600 frameBorder=0></iframe>

---

### Statistics of States above 50 Power-Outages 

### **Category for Causes of Power-Outages**

| Type                          | CA     | MD     | MI     | NY     | PA     | TX     | WA     |
|:------------------------------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| equipment failure             | 10.61% | 0.0%   | 3.16%  | 2.86%  | 1.75%  | 4.1%   | 1.12%  |
| fuel supply emergency         | 5.05%  | 0.0%   | 0.0%   | 17.14% | 0.0%   | 2.46%  | 1.12%  |
| intentional attack            | 12.12% | 43.1%  | 4.21%  | 17.14% | 10.53% | 10.66% | 69.66% |
| islanding                     | 14.14% | 0.0%   | 1.05%  | 0.0%   | 0.0%   | 0.0%   | 3.37%  |
| public appeal                 | 4.55%  | 0.0%   | 1.05%  | 5.71%  | 0.0%   | 13.93% | 1.12%  |
| severe weather                | 33.84% | 55.17% | 87.37% | 47.14% | 84.21% | 52.46% | 22.47% |
| system operability disruption | 19.7%  | 1.72%  | 3.16%  | 10.0%  | 3.51%  | 16.39% | 1.12%  |

### **Severe Weather Causes**

| Weather        | CA     | MD     | MI     | NY     | PA     | TX     | WA    |
|:---------------|:-------|:-------|:-------|:-------|:-------|:-------|:------|
| earthquake     | 1.75%  | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%  |
| flooding       | 0.0%   | 0.0%   | 1.72%  | 0.0%   | 0.0%   | 2.27%  | 0.0%  |
| fog            | 1.75%  | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%  |
| hailstorm      | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 2.27%  | 0.0%  |
| heatwave       | 14.04% | 0.0%   | 0.0%   | 4.55%  | 0.0%   | 0.0%   | 0.0%  |
| heavy wind     | 5.26%  | 11.11% | 17.24% | 9.09%  | 8.11%  | 11.36% | 75.0% |
| hurricanes     | 0.0%   | 7.41%  | 0.0%   | 13.64% | 16.22% | 22.73% | 0.0%  |
| lightning      | 1.75%  | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 2.27%  | 0.0%  |
| snow/ice       | 0.0%   | 3.7%   | 3.45%  | 4.55%  | 8.11%  | 2.27%  | 0.0%  |
| snow/ice storm | 0.0%   | 0.0%   | 1.72%  | 0.0%   | 0.0%   | 0.0%   | 0.0%  |
| storm          | 17.54% | 3.7%   | 10.34% | 13.64% | 5.41%  | 6.82%  | 0.0%  |
| thunderstorm   | 7.02%  | 48.15% | 44.83% | 18.18% | 35.14% | 36.36% | 0.0%  |
| wildfire       | 24.56% | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%  |
| wind           | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%  |
| wind storm     | 1.75%  | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%  |
| wind/rain      | 3.51%  | 0.0%   | 5.17%  | 9.09%  | 5.41%  | 0.0%   | 0.0%  |
| winter         | 0.0%   | 7.41%  | 0.0%   | 0.0%   | 8.11%  | 6.82%  | 0.0%  |
| winter storm   | 21.05% | 18.52% | 15.52% | 27.27% | 13.51% | 6.82%  | 25.0% |

---

## Missingness

### NMAR in the data
There is some reportings in the cause category detail of having a null value. In the case of severe weather, there can be times, where the type of weather is unrecognizable. As a result, there might not be a certain way of classifying the type of weather. There can possibiliy be another column that signifies whether the answer or solution to what caused the power outage is completed with a 1 (meaning they found how) and 0 (unknown). In some cases, where the duration is not recorded, the power outage may be fixed immediately. In other cases, where the number of customers is not recorded, this can be a rural area, where there is no one who is really affected.


### Missingness in Detail of Cause Category

**Comparing the Cause Category with its Detail Cause Category column**
 - We compare when the detail is missing from each cause:

| CAUSE.CATEGORY                |   detail_missing = False |   detail_missing = True |
|:------------------------------|-------------------------:|------------------------:|
| equipment failure             |                0.0451552 |               0.0254777 |
| fuel supply emergency         |                0.0301035 |               0.0403397 |
| intentional attack            |                0.348071  |               0.101911  |
| islanding                     |              nan         |               0.0976645 |
| public appeal                 |              nan         |               0.146497  |
| severe weather                |                0.541863  |               0.397028  |
| system operability disruption |                0.0348071 |               0.191083  |

 - Let us plot missingness in a bar plot:

 <iframe src="assets/detail_missingness.html" width=600 height=600 frameBorder=0></iframe>


---

## Does Power-Outages occur mainly because of wildfires in California?



### Hypothesis Test 



### Conclusion




