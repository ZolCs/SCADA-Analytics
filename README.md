# SCADA Analytics – Industrial Data Simulation and Analysis

## About the Project

This project was developed as part of my practical learning journey in automation, data analysis and business intelligence.

The goal was to build a small SCADA-like environment that demonstrates the complete journey of industrial process data — from configuration and simulated sensor data generation through data storage and analysis to interactive Power BI visualization.

The project was intentionally built step by step, using multiple technologies and focusing not only on the final dashboard, but also on the processes and decisions behind it.

## Project Overview

The system consists of several interconnected components:

- configuration management
- simulated temperature and pressure data generation
- SQLite-based data storage
- Historian-style time-series data
- engineering alert generation
- exploratory data analysis
- temperature-change analysis
- event and process-cycle detection
- feature engineering
- Power BI visualization

The resulting workflow can be summarized as:

Configuration  
↓  
Data Generator  
↓  
Historian Database  
↓  
Data Analytics  
↓  
Event Analysis  
↓  
Power BI Dashboard

## Technologies

- Python
- Pandas
- SQLite
- SQL
- Power BI
- DAX
- Jupyter Notebook
- ODBC
- Git / GitHub

- ## Project Components

### 1. Database Creation

`create_database.ipynb`

Creates the SQLite database structure used by the configuration system.

The database contains the configuration history and the currently active configuration.

---

### 2. Configuration Management

`configuration_input.ipynb`

Creates new configuration records and updates the currently active configuration.

This allows the simulated system to operate using configurable engineering thresholds rather than hard-coded values.

---

### 3. Data Generation

`data_generator_v4.ipynb`

Generates simulated temperature and pressure measurements based on the active configuration.

The generated data is stored in the Historian database together with timestamps and calculated engineering alerts.

---

### 4. Data Analytics

`data_analytics_v1.ipynb`

Loads and prepares the Historian data using Pandas.

The notebook performs exploratory analysis and investigates the distribution of temperature and pressure changes.

The analysis identified several unusual temperature-change patterns that required further investigation.

---

### 5. Event Analysis

`event_analysis_v1.ipynb`

The identified significant temperature changes were investigated as parts of larger process cycles.

Each detected cycle is assigned a unique identifier and a set of descriptive features is calculated, including:

- start and end position
- duration
- minimum and maximum temperature
- total temperature rise
- total temperature fall
- absolute temperature change
- net temperature change

The resulting cycle-level data is stored in a dedicated SQLite database and used by the Power BI report.

## Data Analysis

The exploratory analysis was used to identify patterns in the generated process data.

### Temperature Change Distribution

<img width="526" height="357" alt="Temperature_change" src="https://github.com/user-attachments/assets/cf823068-cdaf-4369-8b8a-65dc4007f7b6" />
<img width="509" height="352" alt="Temperature_change_2" src="https://github.com/user-attachments/assets/c7872395-3a41-4915-80bd-a1f0f9011fb4" />

The histogram revealed a large number of small temperature changes and a smaller number of significant changes.

These observations provided the basis for the subsequent event analysis.

## Power BI Dashboard

The final analysis is presented through an interactive Power BI dashboard.

The report provides several levels of information, starting with the current system state and Historian data and progressing towards statistical and event-level analysis.

### Dashboard Overview

<img width="935" height="525" alt="SCADA_Dashboard" src="https://github.com/user-attachments/assets/b5f8767d-183d-491d-90d6-35df9af167f3" />


### Historian Analysis

<img width="932" height="524" alt="SCADA_alerts" src="https://github.com/user-attachments/assets/be914685-2c28-480f-9ce5-07719ecf169d" />


### Event Analysis

<img width="929" height="526" alt="SCADA_Event" src="https://github.com/user-attachments/assets/537f9120-0451-4f1c-8f75-ce3aa74a47e3" />


## Key Learning Outcomes

This project helped me understand how the different stages of an industrial data workflow connect to each other.

The main areas of learning included:

- designing a simple relational data structure
- working with SQLite databases from Python
- generating and storing time-series process data
- separating configuration from generated process data
- using Pandas for data preparation and analysis
- calculating derived features from process measurements
- identifying and analysing process events
- connecting analytical results to Power BI
- creating dynamic Power BI measures using DAX
- designing a dashboard around the information needs of the user
- organising a multi-stage project in Git and GitHub

One of the most important lessons of the project was that the dashboard is only the final layer of a much larger data workflow.

## Project Status

**Completed – v1.0**

This version represents the completed scope of the Automation project.

Future ideas and more advanced Data Science topics are intentionally outside the scope of this version and may be explored in future projects.

