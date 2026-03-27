# crash-data-mongodb-sqlite-pipeline
End-to-end data pipeline analyzing Colorado motorcycle fatalities (2019–2023) using FARS data. Includes ETL processing, MongoDB → SQLite transformation, and exploratory data analysis with visualizations.

# Crash Data MongoDB → SQLite Pipeline

> End-to-end data pipeline analyzing Colorado motorcycle fatalities (2019–2023) using FARS data. Includes ETL processing, MongoDB → SQLite transformation, and exploratory data analysis with visualizations.

---

## Project Overview

- **Dataset:** FARS (Fatality Analysis Reporting System)  
- **Scope:** Colorado motorcycle fatalities (2019–2023)  
- **Focus:** Identifying trends in crash frequency, location, and time (day vs. night)

---

## Pipeline Architecture
FARS JSON Data (GitHub mirror)
→
Data Extraction & Cleaning (Python)
→
MongoDB Atlas (Raw + semi-structured storage)
→
Transformation / Filtering
→
SQLite (Structured relational model)
→
Analysis & Visualization (Pandas, Matplotlib)


---

## Technologies Used

- Python (Pandas, NumPy, Requests)
- MongoDB Atlas
- SQLite
- Matplotlib
- Jupyter Notebook

---

## Data Processing Steps

### 1. Data Ingestion
- Pulled FARS crash and vehicle datasets (2019–2023)
- Used a GitHub mirror to ensure consistent and reproducible access

### 2. Data Cleaning
- Parsed crash date formats  
- Standardized fields across years  
- Removed incomplete or inconsistent records  

### 3. Motorcycle Filtering
- Filtered vehicle records using **BODY_TYP codes (80–85)**  
- Linked crash records using `ST_CASE`  

### 4. Database Modeling
- Stored raw data in MongoDB  
- Transformed into structured tables in SQLite:
  - `moto_crashes`
  - `moto_vehicles`

### 5. Feature Engineering
- Created **Day vs Night classification**  
- Extracted time-based features (hour, month, year)  
- Aggregated crash counts and fatalities  

---

## Key Insights

- El Paso County had the highest number of motorcycle-related fatal crashes  
- Nighttime crashes accounted for a significant portion of fatalities  
- Crash frequency peaks during warmer months  

---

## Project Structure
```
.
├── data/          # Raw and processed datasets
├── notebooks/     # Jupyter notebooks for analysis
├── scripts/       # ETL and data processing scripts
├── database/      # SQLite database file
├── images/        # Generated visualizations
└── README.md
```


---

## Example Visualizations

- Fatal crashes by county  
- Monthly crash trends  
- Day vs Night comparisons  
- Year-over-year fatality counts  

---

## Purpose

This project demonstrates:

- Building a real-world ETL pipeline  
- Working with both NoSQL and relational databases  
- Cleaning and transforming large public datasets  
- Extracting meaningful insights from structured data  

---

## Future Improvements

- Integrate real-time or more recent crash data  
- Add geospatial visualization (maps)  
- Build a dashboard (Streamlit or Flask)  
- Incorporate additional factors (weather, road conditions)  

---

## Author

**Austin Dachel**  
