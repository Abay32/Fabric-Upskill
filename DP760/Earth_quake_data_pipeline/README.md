# 🌍 Earthquake Data Engineering Project with Microsoft Fabric

---

## 🚀 Project Overview

This project demonstrates how to design and implement a **modern, end-to-end data engineering pipeline** using **Microsoft Fabric**. It showcases how to ingest, process, and analyze real-time earthquake data using a layered architecture aligned with industry best practices.

The pipeline leverages data from the **United States Geological Survey (USGS)** API to build a scalable analytics solution.

👉 **Key objective:**  
Transform raw event data into **analytics-ready datasets** that can drive insights, reporting, and geospatial analysis.

---

## 🏗️ Architecture Overview

The solution follows the **Medallion Architecture**:

### 🔹 Bronze Layer (Raw Ingestion)
- Stores raw earthquake data in its original format
- Minimal transformation
- Ensures data traceability and reproducibility

### 🔹 Silver Layer (Data Refinement)
- Parses nested JSON structures (`geometry`, `properties`)
- Cleans and standardizes data types
- Handles deduplication and late-arriving data
- Applies business logic and enrichment

### 🔹 Gold Layer (Business Analytics)
- Aggregates and structures data for reporting
- Optimizes datasets for performance
- Enables advanced analytics and visualization

---

## 🛠️ Technologies Used

- **Microsoft Fabric**
  - Data Engineering (Spark / Notebooks)
  - Data Factory (Pipelines)
  - Lakehouse (Delta tables)
  - Power BI (Visualization)
- **Python**
- **PySpark**
- **KQL (for analytics and geospatial queries)**

---

## 📥 Data Source

Earthquake event data is sourced from:

🔗 https://earthquake.usgs.gov

The dataset includes:
- Event metadata
- Geospatial coordinates
- Magnitude and classification
- Temporal information

---

## 📂 Repository Structure

### 📘 Bronze Layer Notebook
**`Worldwide Earthquake Events API - Bronze Layer Processing`**

- Ingests raw JSON data from USGS
- Stores data as-is in Lakehouse
- Retains schema flexibility
- Acts as the **system-of-record layer**

---

### 📘 Silver Layer Notebook
**`Worldwide Earthquake Events API - Silver Layer Processing`**

- Parses JSON fields (`geometry`, `properties`)
- Extracts coordinates (longitude, latitude, depth)
- Converts epoch timestamps to proper formats
- Applies **watermarking and deduplication**
- Prepares clean, structured data

---

### 📘 Gold Layer Notebook
**`Worldwide Earthquake Events API - Gold Layer Processing`**

- Performs aggregations and business transformations
- Prepares datasets for reporting and BI tools
- Supports:
  - Trend analysis
  - Magnitude distribution
  - Geospatial insights

---

## 📊 Data Model & Attribute Definitions

- **id** *(string)* → Unique identifier for each earthquake event  
- **latitude** *(double)* → Latitude coordinate  
- **longitude** *(double)* → Longitude coordinate  
- **depth** *(double)* → Depth of the earthquake (km)  
- **title** *(string)* → Event title (magnitude + location)  
- **place** *(string)* → Human-readable location description  
- **sig** *(integer)* → Significance score  
- **mag** *(double)* → Earthquake magnitude  
- **magType** *(string)* → Magnitude scale type  
- **event_time** *(timestamp)* → Time when the earthquake occurred  
- **updated_time** *(timestamp)* → Last update time of the event  

---

## 🌐 Geospatial Capabilities

This project enables **geospatial analytics**, including:

- Creating geo-points from coordinates  
- Distance calculations between events  
- Regional clustering  
- Map-based visualization in Power BI or KQL, python package

