# GEOL0069
# Land Cover Classification over Guangzhou using Sentinel-2 and Machine Learning

## 📌 Project Overview

This project applies supervised machine learning methods to classify land cover types over the Guangzhou region in southern China using Sentinel-2 multispectral satellite imagery. The classification targets four key land cover categories:

- Urban areas
- Cropland
- Forests
- Water bodies

We use both Random Forest (RF) and Convolutional Neural Network (CNN) classifiers, trained on labeled image patches. The project includes IRIS-based manual annotations and evaluates model performance using accuracy metrics and visual inspection. Environmental impact of training is also assessed via `codecarbon`.

---

## 🛰 Remote Sensing Background

Sentinel-2 is a high-resolution multispectral optical imaging mission from the European Space Agency (ESA), providing 10–60m resolution imagery across 13 spectral bands. This project uses:

- Bands: B2 (Blue), B3 (Green), B4 (Red), B8 (NIR)
- Resolution: 10 meters
- Date range: June–September 2023
- Study area: 113.0°E to 113.7°E, 22.8°N to 23.6°N (Guangzhou & surroundings)

---

## 🧠 Methodology

1. **Data Acquisition**  
   Imagery was downloaded from Google Earth Engine and processed into `.tif` and `.npy` formats.

2. **Labeling**  
   Manual labels were created using the IRIS tool, providing ground truth masks for supervised learning.

3. **Classification**  
   Two models were implemented:
   - **Random Forest** using scikit-learn
   - **CNN** using TensorFlow/Keras

4. **Visualization**  
   Prediction results were visualized as color-coded land cover maps.

5. **Model Evaluation**  
   Accuracy, confusion matrix, and intersection-over-union (IoU) were used to compare performance.

6. **Environmental Cost**  
   CodeCarbon was used to assess the carbon footprint of model training.

---

## 🧰 Dependencies & Environment

Install required packages:

```bash
pip install numpy rasterio gdal scikit-learn tensorflow codecarbon matplotlib
