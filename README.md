# SWMPtides <img src="https://r-pkg.org/badges/version-last-release/devtools" align="right"/>

An experimental project for creating an R package for generating visual predictive tide tables for all SWMP stations.  
Be gentle — it's my first R package!  

---

## What the Project Does

The **SWMPtides** package is designed to extract principal tidal constituents from archived observed water level data collected at **NERRS System Wide Monitoring Program (SWMP)** stations.  

From this, the package will generate **tables and plots of future tides and water levels**.  
The package relies heavily on the **TideHarmonics** model and builds upon it to include tools for:  

- Predicting tides for any future month/year  
- Extracting high and low tide events  
- Saving tide tables as CSV files  
- Plotting monthly tide curves with highs/lows  
- *(coming soon)* Calendar-style daily tide summaries  

---

## Why the Project is Useful

If things work out the way I hope, the SWMPtides package will:  

- Acquire NERRS SWMP water quality data  
- Use historical depth data to generate tide tables in `.csv` format  
- Enable plotting of **calendar views** with predicted times and water levels for high and low tides  
- Potentially allow comparisons between **predicted vs. observed water levels**  

In the future, these predictions could also be available as an online tool (e.g. via **Shiny**).  

---

## Installation

This package is currently hosted on GitHub.  

```rhttps://github.com/byrontoothman/SWMPtides/tree/main
# Install devtools if needed
install.packages("devtools")

# Install SWMPtides from GitHub
devtools::install_github("byrontoothman/SWMPtides")

# Also install archived TideHarmonics (dependency)
devtools::install_github("byrontoothman/TideHarmonics")

```

## Example Usage

```r
library(SWMPtides)

# Predict tides for 2025 at the NOCRCWQ station
results <- predict_tides(
  observed_file = "NOCRCWQ2022.csv",
  output_year = 2025,
  station_name = "NOCRCWQ",
  output_dir = "C:/Users/byrontoothman/Documents/tides"
)

# Explore results
head(results$predictions)

# Model summary (tidal constituents)
summary(results$model)

```
