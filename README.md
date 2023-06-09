# State of Ohio Crime Analysis 2017 - 2022

## Context

Often times people move because of a work requirement, have hopes of a different cost of living situation, and/or they enjoy 
what a particular city/state has to offer, entertainment-wise. However, I know in my case I never truly understood 
how safe/unsafe an area has been when deciding to move to a desired city/state.

## Purpose

My intent with this project is to analyze the types of crime that has occurred in Ohio from 2017-2022. This project can be beneficial to current/future Ohio residents and/or government officials. Current and future residents may realize the benefits of this project when they are trying to how safety their local region is. Moreover, government officals can use this information to understand what types of laws, resources, and/or police training/staffing may be needed to deter/reduce crime activity in regions throughout the state.

Questions I would like to answer with my analysis:

      1. What are the major types of crime that has occured?
      2. Are there certain types of crimes that are more common in small, medium, and large cities?
           - OH cities size criteria: Small: <100K, Medium: >100K & <400K, Large: >400K
      4. What is the year-over-year trend of crime ?
      5. Are there any surprises from the crime datasets?

## Prepare Datasets

In this step, I will need to determine what data is needed, locate the necessary data, and decide how I will maintain the data integrity. I've decided to use crime data provided by the criminal justice department listed below. Also, I will search the internet for a listing of Ohio's Cities and respective Counties.

      1.  Ohio's Office of Criminal Justice Services (OCJS) Website for Crime Data Files: <https://dpsoibrspext.azurewebsites.net/?handler=Search>
          - OIBRS_Crime_Data_2022
          - OIBRS_Crime_Data_2021
          - OIBRS_Crime_Data_2020
          - OIBRS_Crime_Data_2019
          - OIBRS_Crime_Data_2018
          - OIBRS_Crime_Data_2017
      2. Ohio's City and County Mapping Source: <https://www.corragroup.com/ohio-county-lookup.html>
   
In order to maintain data integrity, I will do some data cleaning in Excel (using Power Query) and Python. Although it's not efficient to clean data in two different programs, I want to be able to showcase my level of understanding of both programs and how they can be utilize within the Process Data step of the Data Analysis process. Power Query has a feature which records the actions taken on one's dataset and Python's code is repeatable/reproducible by anyone with the same level of coding experience or more.

## Process Data

In this step, I will discuss my data wrangling process used in both Excel and Python for each of my data source files.

- Excel: OCJS Crime datasets: Data Cleaning and Merging Files
 
     1.  Exported Crime Data from OCJS Website for years 2017-2022 onto my personal laptop
     2.  Appended each year's crime data file to one another
     3.  Removed blank rows
     4.  Transposed data into veritical format
     5.  Pivoted all Crime Type into one column
     6.  Removed Property / Violent Crime record counts since their individual offenses have been captured within the file already:
          - Property Crime: includes offenses of burglary, larceny-theft, motor vehicle theft, and arson.
          - Violent Crime: includes offenses of rape, robbery, murder, and aggravated assault
     7.  Created Crime Category column for the crime types mentioned in previous steps
     8.  Extracted Crime Year from each appended file
     9.  Removed all trailing spaces with TRIM function
     10. Named/Verified each column titles/formats appropriately

- Python: Wrangling Cities/Counties via webscraping method

     1.  Read HTML text information (City/Zip Code/County) from Website
     2.  Created data frame for parsed data
     3.  Removed Zip Code attribute since it's out of scope of this project
     4.  Added State name to dataset
     5.  Corrected the county names for 11 cities which had multiple counties mapped to them:
          - Chagrin Falls(Cuyahoga)
          - Cincinnati(Hamilton)
          - Danville(Knox)
          - Dayton(Montgomery)
          - Fairfax(Hamilton)
          - Laurelville(Hocking)
          - Loveland(Hamilton)
          - Northwood(Wood)
          - Riverside(Montgomery)
          - Dillonvale(Jefferson)
          - Lima(Allen)
     7.  Removed null records for City attribute
     8.  Created criteria for City size attribute:
          - Small: < 100K
          - Medium: > 100K & < 400K
          - Large: > 400K
     9.  Inner-joined Crime dataset with Cities and Counties
     10. Exported joined data set into a .csv

## Data Analysis Process

In this step, I will discuss steps taken to analyze my data and gain the necessary insights to satisfy this project's requirements.

In both Excel and Python, I've properly formatted each variable within both datasets which has allowed me to group, perform aggregations and join my datasets accordingly ultimately leading to insights which will be discussed in the following step.

## Visualize Data / Share Insights

Insights gained:

- Crime throughout Ohio state has shown a downward trend from 2017-2022.

![OH_StateWide_Trend_20230630](https://github.com/smcasillas1/Capstone/assets/124643458/494ef731-204f-4bbf-bc0d-025e73ae7cb7)


- Property related crimes saw a downward trend and Violent related crimes saw an uptick at which the Top five crime ridden cities during this time were Cleveland, Columbus, Cincinnati, Toledo and Akron respectively.

![CrimeCategory_20230630](https://github.com/smcasillas1/Capstone/assets/124643458/c89a08fc-29a1-4ce8-9537-51df16634178)


![Top5_Cities_20230630](https://github.com/smcasillas1/Capstone/assets/124643458/86cef325-53f6-4dbd-bea3-b2c8822efa9c)


- I was surprised to learn that Larceny remained the highest crime reported during 2017-2022 while Aggravated Assualts increased consistently 4 of the 5 years reviewed.

![CrimeType_TreeMap_20230630](https://github.com/smcasillas1/Capstone/assets/124643458/b14182e7-48b8-49fc-b3f1-cd885bbd6230)


![CrimeType_Trends_20230630](https://github.com/smcasillas1/Capstone/assets/124643458/03693a4f-ac3b-40f8-848b-2d34585ebbce)

If I was to continue this project, I would analyze the impact COVID had on the reduction in crime as well look at Police staffing levels to see if increases in staff caused the overall reduction.



