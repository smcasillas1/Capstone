# State of Ohio Crime Analysis 2017 - 2022

## Context

Often times people move because of a work requirement, hopes of a different cost of living situation, and/or they enjoy 
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
   
- In order to maintain data integrity, I will do some data cleaning in Excel (using Power Query) and Python. Although it's not efficient to clean data in two different programs, I want to be able to showcase my level of understanding of both programs and how it can be utilize to complete this step within the Data Analysis process. Power Query has a feature which records the actions taken on one's dataset and Python's code is repeatable/reproducible by anyone with the same level of coding experience or more.

## Process Data

- OCJS Crime datasets: Excel Data Cleaning and Merging Datasets
 
     1.  Exported Crime Data from OCJS Website for years 2017-2022 onto my personal laptop
     2.  Appended each crime's year data file together into one file
     3.  Removed blank rows
     4.  Transposed data into veritical format
     5.  Pivoted all crime types into one column
     6.  Pivoted all crime type count into one column
     7.  Named/Verified each column titles appropriately
     8.  Formatted each column appropriately

- Python's Data Cleaning Steps: Wrangling Cities/Counties via webscraping method

     1.  Read HTML text information from Website that contains Ohio City and County Mapping
     2.  Created data frame for parsed data
     3.  Removed Zip Code column since it's out of scope of this project
     4.  Added State Name to add Parent level Hiearchy of the Cities and Counties
     5.  Export content into a .csv

## Data Analysis Process

## Share/Visualize Data


https://www.figma.com/file/oAWaQIYqk64otVDit2BzyF/Capstone-Figma---Sam?node-id=0%3A1&t=rEcEIa6S8iJeYw5q-1
