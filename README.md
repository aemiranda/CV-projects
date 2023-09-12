# Google Analytics 4 Export Transformation
## Overview
During the summer of 2023, I wrote a script in Google BigQuery for my internship. When an organization decides to export raw data from Google Analytics 4 (GA4) to BigQuery daily, the tables that populate BigQuery are separated by date, making it less efficient to query comprehensively. In addition, when connected to BI tools like Metabase, the default nesting feature of the exports may cause certain columns to be difficult to query. Prior to this project, there were no free and comprehensive guides to transforming the raw GA4 exports. This tool is designed to make data queryable, improving data analysis for you and your organization. 

The file GA4_Exports_Transformation_Template contains a looped script written in GoogleSQL that can be used as a template to SELECT columns from the raw data that are relevant to your organization, unnest those nested columns, and split the data into 3 tables: “user_properties”, “event_parameters”, and “main_events”. This script can be pasted into your BigQuery project’s SQL workspace and edited to fit your needs. 

## Setup
Before implementing this script, ensure you have set up daily exports from GA4 to Google BigQuery, with tables in the format “events_YYYYMMDD”. In a separate dataset named “GA4_Data”, create tables “user_properties”, “event_parameters”, and “main_events”. Make sure the schemas match the code in the script or make the appropriate modifications as you see fit. 
