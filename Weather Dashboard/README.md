# 🌦️ Weather Analytics Dashboard (Power BI)

An interactive **Weather Analytics Dashboard** built using **Power BI**, leveraging **REST API integration** to visualize real-time weather and air quality insights across multiple cities.

---

## 📌 Project Overview

This project provides a comprehensive visualization of:

- 🌡️ Current Weather Conditions
- 📅 7-Day Forecast Trends
- 🌫️ Air Quality Index (AQI)
- 🌍 Multi-city Comparison
- 🌅 Sunrise & Sunset Timing

The dashboard transforms raw API data into **actionable insights** using advanced **DAX measures** and interactive visualizations.

---

## 🧰 Tech Stack

- **Power BI Desktop**
- **DAX (Data Analysis Expressions)**
- **REST API (Weather Data Source)**
- **Data Modeling & Transformation**

---

## 🔗 Data Source

- Weather data is fetched dynamically using a **REST API**
- Includes:
  - Temperature (°C / °F)
  - Humidity, Wind Speed, Pressure
  - Air Quality Metrics (PM10, PM2.5, CO, NO2, SO2, O3)

---

## 📊 Key Features

### 🌡️ Real-Time Weather Monitoring
- Displays current temperature, humidity, wind speed, and visibility
- Last updated timestamp included

### 📅 Forecast Visualization
- 7-day temperature trends
- Daily average temperature insights

### 🌫️ Air Quality Analysis
- AQI classification:
  - Good
  - Moderate
  - Unhealthy
  - Hazardous
- Color-coded indicators for better interpretation

### 🌍 Multi-City Dashboard
- Compare weather across cities like:
  - Dhaka
  - Chittagong
  - Khulna
  - Rajshahi
  - Rangpur

### 🌅 Additional Insights
- Sunrise & Sunset timing
- UV Index and precipitation levels

---

## 🎨 Dashboard Backgrounds

<p align="center">
  <img src="https://raw.githubusercontent.com/abusufianrobin/Power_BI_Projects/main/Weather%20Dashboard/Backgrounds/Bg1.PNG" width="250"/>
  <img src="https://raw.githubusercontent.com/abusufianrobin/Power_BI_Projects/main/Weather%20Dashboard/Backgrounds/Bg2.PNG" width="250"/>
  <img src="https://raw.githubusercontent.com/abusufianrobin/Power_BI_Projects/main/Weather%20Dashboard/Backgrounds/Bg3.PNG" width="250"/>
</p>

---

## 📐 DAX Highlights

Some key DAX measures used in this project:

```DAX
AQI_Status_Text = 
    VAR AQI = ROUND(SELECTEDVALUE('Current'[current.air_quality.pm10]),0)
    RETURN SWITCH(
        TRUE(),
        AQI <= 50, "Good",
        AQI <= 100, "Moderate",
        AQI <= 150, "Unhealthy for Sensitive",
        AQI <= 200, "Unhealthy",
        AQI <= 300, "Very Unhealthy",
        "Hazardous"
    )



