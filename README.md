# Uber Business Intelligence GCP Dashboard

### Project summary:
Build a data pipeline to integrate Uber data into Google BigQuery. Create a STAR data model for efficient analysis. Develop an interactive dashboard using Google Looker Analytics to visualize key KPIs.

### Technologies/Tools used:

Google Cloud Storage, SQL, Python, QuickDBD, Google Mage compute engine, Mage.AI Data Pipeline Tool, Google Big Query, Google Looker Analytics, Lucid Chart

Mage.AI is an open-source data pipeline tool that helps with transforming and integrating data, learn more about it here: https://www.mage.ai/

The aim was to become familiar with Google services on the cloud for storing data. Additionally, I wanted to explore more visualization and planning tools such as Looker and Lucid Charts for data modelling. 

Data Model Steps:
- Identified which data points would be part of the dimension or fact tables
- Connected primary keys of the dimension tables to the fact tables via a 1:M relationship
- Used Lucid charts to draft the model, subject to change depending on requirements and scope

<img width="929" alt="Screenshot 2024-10-27 at 12 54 52 PM" src="https://github.com/user-attachments/assets/b723c328-8ea7-4156-a133-eb8b88e4db15">

Google Cloud Steps:

- Ran the virtual machine through GCP, resolved some externally managed environment bugs 
- Downloaded pip and downloaded mage
- Began by using local host and external IP provided by Google Compute Engine

