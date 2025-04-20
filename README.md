# starbucks-analytics
A notebook to create Huff Model probabilities using open source data from various data sources
# ☕ Starbucks Geospatial Customer Analytics

This project applies geospatial analysis and probabilistic modeling to estimate where Starbucks customers in Atlanta are most likely to come from. It combines **Huff modeling**, **Principal Component Analysis (PCA)**, and interactive mapping to visualize consumer behavior around 34 Starbucks locations.

---

## Project Overview

Using demographic zones from across Atlanta and geospatial data for Starbucks store locations, I estimate the **probability that a customer from a given neighborhood will choose a specific Starbucks location**. 

The analysis includes:
- Spatial join of Starbucks stores and neighborhood-level demographics
- Calculation of store **attractiveness** using PCA on variables like traffic, competitor presence, and nearby amenities
- Construction of a **Huff Model** to convert attractiveness and distance into visit probabilities
- Interactive **Folium-based heatmaps** to visualize trade areas per store

---

## What is a Huff Model?

The **Huff Model** is a spatial interaction model that estimates the likelihood of a consumer visiting a particular location based on:
- **Attractiveness**: Features such as accessibility, size, and surrounding POIs
- **Distance Decay**: The idea that farther locations are less likely to be chosen

$$
  P_{ij} = \frac{A_j^\lambda}{D_{ij}^\beta} \Big/ \sum_k \frac{A_k^\lambda}{D_{ik}^\beta}
$$

---

## 🛠️ Technologies Used

- **Python**
  - `GeoPandas`, `Shapely`, `NumPy`, `Pandas`
  - `scikit-learn` for PCA
  - `Folium` for interactive maps
- **Jupyter Notebook** for exploratory analysis
- **GeoJSON & shapefiles** for spatial data

---

## Outputs

- A **distance matrix** from each demographic zone to each Starbucks
- A computed **attractiveness score** per store using PCA
- **Huff probability matrix** (zones × stores)
- **Interactive heatmaps** for visualizing store trade areas

---

## Applications

- Targeted **marketing campaigns** by neighborhood
- Data-driven **site selection** for future store openings
- Enhanced **operational planning** and customer segmentation
- Integration with **sales or foot traffic** data to validate predictions

---

## Getting Started

Clone the repo and open `starbucks_analytics.ipynb` in Jupyter:

```bash
git clone https://github.com/your-username/starbucks-analytics.git
cd starbucks-analytics
jupyter notebook
