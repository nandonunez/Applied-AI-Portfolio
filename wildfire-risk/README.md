


# Wildfire Risk Prediction System (SOM-based)


## 🏗 System Architecture
```mermaid
graph LR
      A[User or Client Request] --> B[Automated GFS Data Download]
      B --> C[Data Preprocessing and Variable Extraction]
      C --> D[SOM Model: Climate Pattern Classification]
      D --> E[Risk Index Calculation using Historical Fire Data]
      E --> F[Risk Category Mapping: Very Low, Low, Medium, High]
      F --> G[API Delivery to Client Database]
```


<p align="center" style="font-size: 0.9em; color: #888;">
   <em>Illustration: Training process of a Self-Organizing Map (SOM). Source: <a href="https://commons.wikimedia.org/wiki/File:Somtraining.svg">Wikimedia Commons</a></em>
</p>

---

## 🔍 Overview

This system leverages global weather forecasts (GFS) and historical wildfire data to deliver operational wildfire risk predictions. Using a Self-Organizing Map (SOM), the pipeline classifies meteorological patterns and assigns risk indices based on historical fire occurrence and severity. The results are mapped to actionable risk categories and delivered via API for integration into client systems.

### **Key Features**
- **Automated Data Pipeline:** Downloads and processes the latest GFS weather data for any region of interest.
- **Flexible Configuration:** Easily adjust variables, levels, and region in the config file.
- **Unsupervised Pattern Discovery:** SOM model identifies climate patterns most associated with large fire events.
- **Risk Quantification:** Each SOM neuron is assigned a risk index, derived from the proportion of large fires (>500 ha) relative to all significant fires (>5 ha) historically mapped to that pattern.
- **Actionable Output:** Risk is categorized (Very Low, Low, Medium, High) and delivered programmatically for operational use.

### **Workflow**
1. **Data Acquisition:** Automated download of the latest GFS weather data (wind, temperature, humidity, etc.).
2. **Preprocessing:** Cleans, formats, and extracts relevant meteorological variables.
3. **Pattern Classification:** Applies a pre-trained SOM to classify the current forecast into a climate pattern.
4. **Risk Index Assignment:** Assigns a risk index to the pattern using historical fire data and neuron assignment.
5. **Risk Mapping & Delivery:** Maps the risk index to a category and delivers the result via API to client databases.

---


## 🎯 Impact

* **Challenge:** High climate variability and data complexity make wildfire risk prediction and management difficult.
* **Solution:** The system enables anticipation of high-risk zones and preparation of fire prediction and response services, supporting decision-making and resource allocation.
* **Application:** Used by emergency and planning teams to prioritize critical areas and improve response to extreme events.

---

## 🛠 Tech Stack

* **Machine Learning:** scikit-learn, MiniSom
* **Data Processing:** pandas, numpy, xarray
* **Weather Data:** GFS (NOAA)
* **Deployment:** Python scripts, Docker
* **Formats:** GRIB, CSV, Parquet

---




**Note:** This repository is a technical demonstration and does not include sensitive data or proprietary code.
