# Overview
This project is a part of my build in public challenge on twitter. The dataset used for this challenge is anime dataset from Kaggle.The project is intended to analyze and generate the insights for anime industry.
# Prerequisites
Before running the DAG, ensure you have the following prerequisites:

1. Apache Airflow installed and configured.
2. Python dependencies installed, including pandas.

# File Structure
1. etl_orchestrator.py: The main DAG file containing the workflow logic.
2. anime.csv: Sample CSV file for data ingestion.

# DAG Structure
# Tasks
<b> Data Ingestion (data_ingestion):</b>

1. Reads the CSV data from anime.csv.
2. Validates the existence of the file before reading.

<b>Data Cleaning (data_cleaning):</b>

1. Removes empty columns.
2. Drops duplicate rows.
3. Normalizes column names.

<b> Transformation (transformation):</b>

1. Applies various transformations to the data:
2. Fills missing numeric values with the mean.
3. Fills missing float values with the mean.
4. Fills missing categorical values with the mode.


<b> Save to CSV (save_to_csv):</b>

<li>Saves the transformed data to a CSV file named transformed_data.csv.</li>


<b>Workflow</b>

<li>The workflow follows the sequence: data_ingestion ➔ data_cleaning ➔ transformation  ➔ save_to_csv. </li>

# Usage

1. Ensure that Apache Airflow is up and running.

2. Place the CSV file (anime.csv) in the same directory as etl_orchestrator.py.

3. Copy the DAG file (etl_orchestrator.py) to the DAGs directory of your Apache Airflow installation.

4. Access the Airflow web interface and trigger the DAG manually.(This project is in progress so it's scheduled manually).

# Note

1. The DAG is configured with schedule_interval=None, indicating it needs to be triggered manually.

2. Adjust the file paths as per your requirements.

