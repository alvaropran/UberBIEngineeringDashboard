# Uber Business Intelligence GCP Dashboard

### Project summary:
Build a data pipeline to integrate Uber data into Google BigQuery. Create a STAR data model for efficient analysis. Develop an interactive dashboard using Google Looker Analytics to visualize key KPIs.

### Technologies/Tools used:

Google Cloud Storage, SQL, Python, QuickDBD, Google Mage compute engine, Mage.AI Data Pipeline Tool, Google Big Query, Google Looker Analytics, Lucid Chart

Mage.AI is an open-source data pipeline tool that helps with transforming and integrating data, learn more about it here: https://www.mage.ai/

The aim was to explore key insights on real Uber data and become familiar with Google services on the cloud for storing data. Additionally, I wanted to explore more visualization and planning tools such as Looker and Lucid Charts for data modelling. 

## Architecture 

<img width="625" alt="Screenshot 2024-10-27 at 3 12 00 PM" src="https://github.com/user-attachments/assets/1c429fa6-1942-49ec-993d-eb61ee5dde1b">

___
## Key Findings/Insights

Through dynamic and interactive data visualizations, I revealed critical insights into Uber's key performance indicators (KPIs) such as driver productivity, rider retention, and revenue generation. By identifying trends and patterns in these metrics, I provided a comprehensive understanding of operational performance, helping stakeholders address inefficiencies and capitalize on opportunities.

I empowered business users by developing intuitive, user-friendly dashboards that are both visually appealing and highly customizable. These dashboards enable users at all levels to effortlessly access, analyze, and interpret data, fostering a culture of data-driven decision-making. This approach ensures that insights are not confined to technical teams but are readily available to support strategic planning and day-to-day operations.

Furthermore, I demonstrated the transformative power of comprehensive data analytics tools in deriving actionable business intelligence. By leveraging advanced analytical techniques, I helped translate raw data into meaningful insights, guiding strategic initiatives that drive growth and improve customer satisfaction. This process underscored the importance of robust data infrastructure in staying competitive in a dynamic business landscape.


___
## Step 1: Data Modelling

### Data Model Steps:
- Identified which data points would be part of the dimension or fact tables
- Connected primary keys of the dimension tables to the fact tables via a 1:M relationship
- Used Lucid charts to draft the model, subject to change depending on requirements and scope

### Tables used:

Fact Table: 
Quantitative measures or metrics used for analysis
Foreign keys that link to dimension tables
Contains columns that change frequently
Contains columns not useful for analysis, but essential for calculating metrics

Dimension Table:
Columns describe attributes of data being analyzed
Primary keys linking to fact tables
Low cardinality dont change frequently
Summary: Static, don’t change, product names

Below is the STAR schema model:

<img width="929" alt="Screenshot 2024-10-27 at 12 54 52 PM" src="https://github.com/user-attachments/assets/b723c328-8ea7-4156-a133-eb8b88e4db15">

### Data Preparation and Transformation:

Data Import: Load the flat file into a Python DataFrame.
Data Cleaning:
- Identify and handle missing values (e.g., fill with appropriate values or remove rows).
- Convert relevant columns to appropriate data types (e.g., convert date/time strings to datetime objects using pd.to_datetime()).
Data Standardization:
- Standardize date and time formats.
- Remove unnecessary characters or whitespace.
- Identify and handle outliers if necessary.

### Dimension Table Creation:

Determine the key dimensions from the data (e.g., date, time, location, vehicle type). Extract Dimension Attributes: Extract relevant attributes from the data (e.g., hour, day, month, year, weekday).

#### Create Dimension Tables:
- Identify unique records for each dimension.
- Assign a unique identifier (e.g., ID) to each record.
- Structure the data into dimension tables with appropriate columns (e.g., dimension ID, dimension attributes).

#### Fact Table Creation:
- Determine the key metrics or measures to be stored in the fact table (e.g., trip distance, fare amount, tip amount).
- Join the dimension tables to the fact table based on common keys (e.g., date ID, time ID, location ID).
- Include the fact measures in the fact table.
- Structure the fact table with appropriate columns (e.g., foreign keys to dimension tables, fact measures).

#### Additional Considerations:
- Data Dictionary: Refer to the data dictionary to understand the meaning and usage of different data elements.
- Ensure data quality by performing data validation and cleansing.
- Consider techniques like indexing and partitioning to improve query performance.
- Implement appropriate security measures to protect sensitive data.
___
## Step 2: Set up Google Cloud Storage

Setting Up a Data Pipeline with Google Cloud

- Create a Google Cloud Project and Storage Bucket:
  - Set up a new Google Cloud Platform project login using a free trial, comes with $300 credit.
  - Create a storage bucket to store my data.
  - Upload the data to the bucket.
  
- Create a Google Compute Engine Instance:
  - Launch a virtual machine instance SSH.
  - Choose a suitable region and machine configuration.

- Set Up the Environment:
  - Address any bugs or inconsistencies related to the external environment.
  - Install required packages like pip and mage.

- Configure Firewall Rules:
  - Create a firewall rule to allow incoming traffic to the instance on the specified port, this port is identified when mage is run on the VM.
  - Set the source IP address range to 0.0.0.0/0 to allow access from anywhere.
    
- Run The Application: Initial Testing: Start your application using localhost and the external IP provided by Google Compute Engine to test its functionality.


Command List: Refer to the specific command list for detailed instructions on how to perform these tasks. --> [Text Commands Here](commands.txt)
___

## Step 3: Mage.AI steps (Load, Transform, Extract)

- Python Transformation Code done in Jupyter Notebook can be found in the file directory
- Edit io_config.yaml to match with GCP credentials (project name, key, location, etc.)
Steps: NAvigate to GCP API → Create new credential → Service Account → Create new keys → Download keys
- Enter keys to io_config.yaml, this is how we get the proper credentials and gateways
___

## Step 4: Write SQL Queries for GCP Google Big Query

The SQL queries aim to analyze the data so that it can be easily used in Google Looker Studio and further.
___

## Step 5: Looker Dashboard

Create an interactive looker dashboard with valuable KPI's

<img width="768" alt="Screenshot 2024-11-15 at 11 33 46 AM" src="https://github.com/user-attachments/assets/2ecd0847-45af-4422-8dfc-cd6a141f6162">


