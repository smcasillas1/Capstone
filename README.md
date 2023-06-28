# State of Ohio Crime Analysis 2017 - 2022

## Context

Often times people move because of a work requirement, have hopes of a different cost of living situation, and/or they enjoy 
what a particular city/state entertainment scene. However, I know in my case I never truly understood 
how safe/unsafe an area has been when deciding to move to a desired city/state.

## Purpose

My intent with this project is to conduct an analysis on the types of crime that has occurred for an entire state. This project can 
be beneficial to anyone who would like to understand crimes in Ohio - current/future Ohio residents and/or government officials 
who want to understand how crime has trended from 2017-2022 in Ohio. The latter audience can also use this information to understand 
what types of laws, resources, and/or police training/staffing may be needed to deter/reduce the types of crimes that have occurred
in different parts of the state.

  - Questions I would like to answer with my analysis:

      1. What are the major types of crime that occurs in Ohio by City/County?
      2. Are there certain types of crimes that are more common in small, medium, and large cities?
           - OH cities size criteria: Small: <100K, Medium: >100K & <400K, Large: >400K
      4. What is the year-over-year trend of crime throughout Ohio?
      5. Are there any surprises from the crime datasets?

## Prepare Datasets

  - In this step I will need to determine what data is needed, identify where this data is located, and decide how I will maintain the data integrity. At which I've decided to use crime data provided by the criminal justice department listed below. Also, I will search the internet for a listing of Ohio's Cities and respective Counties.
      1.  Ohio's Office of Criminal Justice Services (OCJS) Website for Crime Data Files: <https://dpsoibrspext.azurewebsites.net/?handler=Search>
          - OIBRS_Crime_Data_2022
          - OIBRS_Crime_Data_2021
          - OIBRS_Crime_Data_2020
          - OIBRS_Crime_Data_2019
          - OIBRS_Crime_Data_2018
          - OIBRS_Crime_Data_2017
      2. Ohio's City and County Mapping Source: <https://www.whereig.com/usa/zipcodes/ohio.html](https://www.corragroup.com/ohio-county-lookup.html>
   
- In order to maintain data integrity, I will do some data cleaning in Excel (using Power Query) and Python. Although it's not efficient to clean data in two different programs, I want to be able to showcase my level of understanding of both programs and how they can be utilize within the Process Data step of the Data Analysis process. Power Query has a feature which records the actions taken on one's dataset and Python's code is repeatable/reproducible by anyone with the same level of coding experience or more.

## Process Data

- OCJS Crime datasets: Excel Data Cleaning and Merging Datasets
 
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

- Python's Data Cleaning Steps: Wrangling Cities/Counties via webscraping method

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

- Has your data been properly formatted?
     1.  Yes, I've properly formatted each variable within both datasets.
- How should you organize your data to perform analysis on it?
     1.  I have joined the crime dataset and city/county files to understand how crime has occurred in each city/county within Ohio.
- What trends or relationships did you find in the data?
     1.  During COVID, Property related crimes saw a downward trend and Violent related crimes saw an upward trend.
     2.  The Top 5 cities that had the highest concentration of crime were Cleveland, Columbus, Cincinnati, Toledo and Akron.
- What surprises did you discover in the data?
     1.   I was surprised to see that Larceny is the leading crime throughout the state of Ohio.
     2.   I was also surprised to see that Aggravated Assualts was the only crime type that expereinced consistent upticks 4 of the 5 years analyzed.
- How will these insights help answer your business questions?



## Visualize Data / Share Insights



https://www.figma.com/file/oAWaQIYqk64otVDit2BzyF/Capstone-Figma---Sam?node-id=0%3A1&t=rEcEIa6S8iJeYw5q-1
