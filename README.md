# Data Analysis: Power-Outages in California 📊

### February 2023

---

## Introduction

Electricity is indispensable. From the lights in our room and to the screens of our electronic devices, we need electricity.

However, what if we suddenly just lose that power and everything goes dark?
This would be a total nightmare. No lights but only darkness. 

This is why we should study power-outages! 

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

**Overview of Raw Dataset**

| Major power outage events in the continental U.S.                                                           | Unnamed: 1   | Unnamed: 2   | Unnamed: 3   | Unnamed: 4   | Unnamed: 5   | Unnamed: 6   | Unnamed: 7         | Unnamed: 8    | Unnamed: 9       | Unnamed: 10                      | Unnamed: 11                  | Unnamed: 12                      | Unnamed: 13                  | Unnamed: 14        | Unnamed: 15           | Unnamed: 16     | Unnamed: 17     | Unnamed: 18    | Unnamed: 19        | Unnamed: 20           | Unnamed: 21           | Unnamed: 22           | Unnamed: 23           | Unnamed: 24   | Unnamed: 25   | Unnamed: 26   | Unnamed: 27   | Unnamed: 28   | Unnamed: 29   | Unnamed: 30   | Unnamed: 31   | Unnamed: 32   | Unnamed: 33   | Unnamed: 34     | Unnamed: 35   | Unnamed: 36   | Unnamed: 37   | Unnamed: 38      | Unnamed: 39    | Unnamed: 40    | Unnamed: 41       | Unnamed: 42   | Unnamed: 43   | Unnamed: 44   | Unnamed: 45   | Unnamed: 46   | Unnamed: 47   | Unnamed: 48   | Unnamed: 49             | Unnamed: 50             | Unnamed: 51             | Unnamed: 52   | Unnamed: 53   | Unnamed: 54   | Unnamed: 55   | Unnamed: 56      |
|:------------------------------------------------------------------------------------------------------------|:-------------|:-------------|:-------------|:-------------|:-------------|:-------------|:-------------------|:--------------|:-----------------|:---------------------------------|:-----------------------------|:---------------------------------|:-----------------------------|:-------------------|:----------------------|:----------------|:----------------|:---------------|:-------------------|:----------------------|:----------------------|:----------------------|:----------------------|:--------------|:--------------|:--------------|:--------------|:--------------|:--------------|:--------------|:--------------|:--------------|:--------------|:----------------|:--------------|:--------------|:--------------|:-----------------|:---------------|:---------------|:------------------|:--------------|:--------------|:--------------|:--------------|:--------------|:--------------|:--------------|:------------------------|:------------------------|:------------------------|:--------------|:--------------|:--------------|:--------------|:-----------------|
| Time period: January 2000 - July 2016                                                                       | nan          | nan          | nan          | nan          | nan          | nan          | nan                | nan           | nan              | nan                              | nan                          | nan                              | nan                          | nan                | nan                   | nan             | nan             | nan            | nan                | nan                   | nan                   | nan                   | nan                   | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan             | nan           | nan           | nan           | nan              | nan            | nan            | nan               | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan                     | nan                     | nan                     | nan           | nan           | nan           | nan           | nan              |
| Regions affected: Outages reported in this data file affected a single U.S. state at the time of occurrence | nan          | nan          | nan          | nan          | nan          | nan          | nan                | nan           | nan              | nan                              | nan                          | nan                              | nan                          | nan                | nan                   | nan             | nan             | nan            | nan                | nan                   | nan                   | nan                   | nan                   | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan             | nan           | nan           | nan           | nan              | nan            | nan            | nan               | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan                     | nan                     | nan                     | nan           | nan           | nan           | nan           | nan              |
| nan                                                                                                         | nan          | nan          | nan          | nan          | nan          | nan          | nan                | nan           | nan              | nan                              | nan                          | nan                              | nan                          | nan                | nan                   | nan             | nan             | nan            | nan                | nan                   | nan                   | nan                   | nan                   | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan             | nan           | nan           | nan           | nan              | nan            | nan            | nan               | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan                     | nan                     | nan                     | nan           | nan           | nan           | nan           | nan              |
| nan                                                                                                         | nan          | nan          | nan          | nan          | nan          | nan          | nan                | nan           | nan              | nan                              | nan                          | nan                              | nan                          | nan                | nan                   | nan             | nan             | nan            | nan                | nan                   | nan                   | nan                   | nan                   | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan             | nan           | nan           | nan           | nan              | nan            | nan            | nan               | nan           | nan           | nan           | nan           | nan           | nan           | nan           | nan                     | nan                     | nan                     | nan           | nan           | nan           | nan           | nan              |
| variables                                                                                                   | OBS          | YEAR         | MONTH        | U.S._STATE   | POSTAL.CODE  | NERC.REGION  | CLIMATE.REGION     | ANOMALY.LEVEL | CLIMATE.CATEGORY | OUTAGE.START.DATE                | OUTAGE.START.TIME            | OUTAGE.RESTORATION.DATE          | OUTAGE.RESTORATION.TIME      | CAUSE.CATEGORY     | CAUSE.CATEGORY.DETAIL | HURRICANE.NAMES | OUTAGE.DURATION | DEMAND.LOSS.MW | CUSTOMERS.AFFECTED | RES.PRICE             | COM.PRICE             | IND.PRICE             | TOTAL.PRICE           | RES.SALES     | COM.SALES     | IND.SALES     | TOTAL.SALES   | RES.PERCEN    | COM.PERCEN    | IND.PERCEN    | RES.CUSTOMERS | COM.CUSTOMERS | IND.CUSTOMERS | TOTAL.CUSTOMERS | RES.CUST.PCT  | COM.CUST.PCT  | IND.CUST.PCT  | PC.REALGSP.STATE | PC.REALGSP.USA | PC.REALGSP.REL | PC.REALGSP.CHANGE | UTIL.REALGSP  | TOTAL.REALGSP | UTIL.CONTRI   | PI.UTIL.OFUSA | POPULATION    | POPPCT_URBAN  | POPPCT_UC     | POPDEN_URBAN            | POPDEN_UC               | POPDEN_RURAL            | AREAPCT_URBAN | AREAPCT_UC    | PCT_LAND      | PCT_WATER_TOT | PCT_WATER_INLAND |
| Units                                                                                                       | nan          | nan          | nan          | nan          | nan          | nan          | nan                | numeric       | nan              | Day of the week, Month Day, Year | Hour:Minute:Second (AM / PM) | Day of the week, Month Day, Year | Hour:Minute:Second (AM / PM) | nan                | nan                   | nan             | mins            | Megawatt       | nan                | cents / kilowatt-hour | cents / kilowatt-hour | cents / kilowatt-hour | cents / kilowatt-hour | Megawatt-hour | Megawatt-hour | Megawatt-hour | Megawatt-hour | %             | %             | %             | nan           | nan           | nan           | nan             | %             | %             | %             | USD              | USD            | fraction       | %                 | USD           | USD           | %             | %             | nan           | %             | %             | persons per square mile | persons per square mile | persons per square mile | %             | %             | %             | %             | %                |
| nan                                                                                                         | 1            | 2011         | 7            | Minnesota    | MN           | MRO          | East North Central | -0.3          | normal           | Friday, July 1, 2011             | 5:00:00 PM                   | Sunday, July 3, 2011             | 8:00:00 PM                   | severe weather     | nan                   | nan             | 3060            | nan            | 70000              | 11.6                  | 9.18                  | 6.81                  | 9.28                  | 2332915       | 2114774       | 2113291       | 6562520       | 35.54907261   | 32.22502941   | 32.20243138   | 2308736       | 276286        | 10673         | 2595696         | 88.9448       | 10.6440       | 0.4112        | 51268            | 47586          | 1.077375699    | 1.6               | 4802          | 274182        | 1.751391412   | 2.2           | 5348119       | 73.27         | 15.28         | 2279                    | 1700.5                  | 18.2                    | 2.14          | 0.6           | 91.59266587   | 8.407334131   | 5.478742983      |
| nan                                                                                                         | 2            | 2014         | 5            | Minnesota    | MN           | MRO          | East North Central | -0.1          | normal           | Sunday, May 11, 2014             | 6:38:00 PM                   | Sunday, May 11, 2014             | 6:39:00 PM                   | intentional attack | vandalism             | nan             | 1               | nan            | nan                | 12.12                 | 9.71                  | 6.49                  | 9.28                  | 1586986       | 1807756       | 1887927       | 5284231       | 30.03248722   | 34.21038936   | 35.72756376   | 2345860       | 284978        | 9898          | 2640737         | 88.8335       | 10.7916       | 0.3748        | 53499            | 49091          | 1.089792426    | 1.9               | 5226          | 291955        | 1.790001884   | 2.2           | 5457125       | 73.27         | 15.28         | 2279                    | 1700.5                  | 18.2                    | 2.14          | 0.6           | 91.59266587   | 8.407334131   | 5.478742983      |
| nan                                                                                                         | 3            | 2010         | 10           | Minnesota    | MN           | MRO          | East North Central | -1.5          | cold             | Tuesday, October 26, 2010        | 8:00:00 PM                   | Thursday, October 28, 2010       | 10:00:00 PM                  | severe weather     | heavy wind            | nan             | 3000            | nan            | 70000              | 10.87                 | 8.19                  | 6.07                  | 8.15                  | 1467293       | 1801683       | 1951295       | 5222116       | 28.09767152   | 34.50101453   | 37.36598344   | 2300291       | 276463        | 10150         | 2586905         | 88.9206       | 10.6870       | 0.3924        | 50447            | 47287          | 1.066825978    | 2.7               | 4571          | 267895        | 1.706265514   | 2.1           | 5310903       | 73.27         | 15.28         | 2279                    | 1700.5                  | 18.2                    | 2.14          | 0.6           | 91.59266587   | 8.407334131   | 5.478742983      |
| nan                                                                                                         | 4            | 2012         | 6            | Minnesota    | MN           | MRO          | East North Central | -0.1          | normal           | Tuesday, June 19, 2012           | 4:30:00 AM                   | Wednesday, June 20, 2012         | 11:00:00 PM                  | severe weather     | thunderstorm          | nan             | 2550            | nan            | 68200              | 11.79                 | 9.25                  | 6.71                  | 9.19                  | 1851519       | 1941174       | 1993026       | 5787064       | 31.99409925   | 33.54333043   | 34.43932882   | 2317336       | 278466        | 11010         | 2606813         | 88.8954       | 10.6822       | 0.4224        | 51598            | 48156          | 1.071476036    | 0.6               | 5364          | 277627        | 1.932088738   | 2.2           | 5380443       | 73.27         | 15.28         | 2279                    | 1700.5                  | 18.2                    | 2.14          | 0.6           | 91.59266587   | 8.407334131   | 5.478742983      |

---

## Exploratory Data Analysis

---

### Data Cleaning



### Visualizations



### Statistics of States above 50 Power-Outages 

---

## Missingness



### NMAR in the data



### Total Variation Distance

---

## Does Power-Outages occur mainly because of wildfires in California?



### Hypothesis Test 



### Conclusion




