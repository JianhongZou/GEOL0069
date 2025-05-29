# GEOL0069
# Sentinel-2 Water Body Detection using NDWI, MNDWI, and K-means Clustering

## Overview

This project aims to detect and classify inland water bodies in China's **Yangtze River Delta (Poyang Lake)** and **Pearl River Delta (Zhujiang River)** regions using Sentinel-2 imagery. The workflow integrates spectral indices (NDWI, MNDWI) with unsupervised **K-means clustering** to improve water extraction accuracy.

## Objectives

- Extract surface water from Sentinel-2 images using NDWI and MNDWI
- Apply K-means clustering on spectral bands and indices to classify water/non-water areas
- Compare classification results with NDWI baseline masks

---

## Data

- **Satellite**: Sentinel-2 MSI Level-1C
- **Bands used**:
  - B3 (Green, 10m)
  - B8 (NIR, 10m) – for NDWI
  - B11 (SWIR, 20m resampled to 10m) – for MNDWI
- **Regions of Interest**:
  - Yangtze River Delta (Poyang Lake area)
  - Pearl River Delta (Zhujiang / Guangzhou area)

---

## Methods

### 1. **NDWI (Normalized Difference Water Index)**
- Formula: `(Green - NIR) / (Green + NIR)`
- Used to generate binary water masks (1 = water, 0 = non-water)

### 2. **MNDWI (Modified NDWI)**
- Formula: `(Green - SWIR) / (Green + SWIR)`
- More effective in urban or turbid areas

### 3. **K-means Clustering**
- Applied to:
  - Band combinations (e.g., Green + NIR or Green + SWIR)
  - MNDWI values
- Automatically labels pixels into water / non-water clusters
- Post-processing step flips labels based on NIR or MNDWI statistics

---

## Structure

```bash
├── data/                    # Sentinel-2 JP2 files
├── scripts/                 # Jupyter Notebooks and Python scripts
├── outputs/                 # Classification results and masks
├── README.md

