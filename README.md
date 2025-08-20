# EARTHQUAKE-PYTHON-POWER-BI
This project analyzes global earthquake data using the USGS Earthquake API. The workflow demonstrates skills in API pulling, Python data wrangling, and Power BI visualization, with insights into earthquake patterns across countries.
🚀 Project Workflow

🛠️ Tech Stack
Python: requests, pandas, datetime
API: USGS Earthquake API
Power BI: Interactive dashboard & KPIs
Excel: Used for Data Cleaning & preprocessing

Data Collection (Python)

Pulled earthquake data (GeoJSON) from the USGS Earthquake API (Python)

Extracted features:
-- Date
-- Magnitude
-- Place
-- Depth (km)
-- Latitude & Longitude
-- Country

Data Wrangling (Python & Excel)
-- Converted nested JSON to a structured CSV file.
-- Created a Magnitude Category column:
            Moderate (5–6),High (6–8),Very High (>8)
-- Cleaned country names for consistency.

Visualization (Power BI)
-- Total Earthquakes → KPI Card.
-- Strongest EQ Country → DAX-based measure. 
           { StrongestEQCountry = 
FIRSTNONBLANK(
    TOPN(
        1,
        VALUES(Earthquake[Country]),
        CALCULATE(MAX(earthquake[Magnitude])),
        DESC
    ),
    1
)

}
-- India Total EQ
-- Total EQ by Year → Line Chart
-- Total EQ by Depth Level → Column Chart
-- Top 10 Countries by Earthquakes → Bar Chart.
-- Bottom 10 Countries by Earthquakes → Bar Chart.
-- Total EQ by Magnitude Level Categories Distribution → Bar Chart.
-- Earthquake Map  → Filled Map visualization.



<img width="1346" height="743" alt="Screenshot (528)" src="https://github.com/user-attachments/assets/a709d6eb-39c0-4cd0-b00a-db653a392ac9" />
