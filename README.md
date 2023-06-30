# State of Ohio Crime Analysis 2017 - 2022

## Context

Often times people move because of a work requirement, have hopes of a different cost of living situation, and/or they enjoy 
what a particular city/state entertainment scene. However, I know in my case I never truly understood 
how safe/unsafe an area has been when deciding to move to a desired city/state.

## Purpose

My intent with this project is to conduct an analysis on the types of crime that has occurred for an entire state. This project can 
be beneficial to anyone who would like to understand crimes in Ohio such as current/future Ohio residents and/or government officials 
that are interested in crime activity trends from 2017-2022. The latter audience can also use this information to understand 
what types of laws, resources, and/or police training/staffing may be needed to deter/reduce the types of crimes that have occurred
in different parts of the state.

  - Questions I would like to answer with my analysis:

      1. What are the major types of crime that occurs in Ohio by City/County?
      2. Are there certain types of crimes that are more common in small, medium, and large cities?
           - OH cities size criteria: Small: <100K, Medium: >100K & <400K, Large: >400K
      4. What is the year-over-year trend of crime throughout Ohio?
      5. Are there any surprises from the crime datasets?

## Prepare Datasets

In this step I will need to determine what data is needed, identify where this data is located, and decide how I will maintain the data integrity. At which I've decided to use crime data provided by the criminal justice department listed below. Also, I will search the internet for a listing of Ohio's Cities and respective Counties.
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

In this step, I will discuss steps taken to analyze my data and gain the necessary insights to satisfy this project's requirements.

I've properly formatted each variable within both datasets which will allow me to perform calculations, grouping, and joining my datasets accordingly to gain the necessary insights that will fulfill this project's purpose.

By performing various groupings while summing up the crime totals I was able to discover that during COVID, Property related crimes saw a downward trend and Violent related crimes saw an uptick at which the Top five crime ridden cities during the time analyzed were Cleveland, Columbus, Cincinnati, Toledo and Akron respectively. 

I was surprised to learn that Larceny remained the highest crime reported during 2017-2022; while Aggravated Assualts increased consistently 4 of the 5 years analyzed.

## Visualize Data / Share Insights

- What story does your data tell? 


