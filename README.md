# PAN-AQI: Panoramic Air Quality Index Dataset

> Sample Dataset: [Link](https://drive.google.com/drive/folders/1GFeq8R9x1v6XVYOurSx4VU9hY88SPeI5?usp=sharing)
>
> This repository currently provides a sample subset of the PAN-AQI dataset. The complete PAN-AQI dataset contains 33,982 panoramic 360° images collected across Hyderabad and Secunderabad, India, along with co-located environmental measurements. Information regarding the full dataset release will be shared in the future.

---

## Overview

PAN-AQI is a large-scale panoramic image dataset designed for urban air quality estimation using computer vision and multimodal learning techniques.

The complete PAN-AQI dataset contains **33,982 panoramic street-view images** paired with environmental measurements including:

* PM2.5 concentration
* PM10 concentration
* Air Quality Index (AQI)
* Temperature
* Relative Humidity
* Timestamp metadata

The dataset was collected across Hyderabad and Secunderabad, India, covering approximately **1000 km** of urban road networks and spanning **Summer, Monsoon, and Winter** seasons.

This repository provides a **sample subset** of PAN-AQI to illustrate the dataset structure and annotation format.

---

## Key Features

* Panoramic 360° street-view imagery
* Co-located air quality measurements
* PM2.5 and PM10 pollutant readings
* AQI labels computed using CPCB guidelines
* Temperature and humidity metadata
* Multi-season urban environmental coverage
* Suitable for multimodal learning and environmental monitoring research

---

## Dataset Structure

```text
PAN-AQI
│
├── PAN_AQI.csv
│
└── Images
    ├── 1.jpg
    ├── 2.jpg
    ├── 3.jpg
    ├── ...
    └── N.jpg
```

### PAN_AQI.csv

Each row corresponds to a single panoramic image and its associated environmental measurements.

Example columns:

| Column      | Description                 |
| ----------- | --------------------------- |
| Image_ID    | Image filename              |
| Timestamp   | Capture timestamp           |
| Temperature | Ambient temperature (°C)    |
| Humidity    | Relative humidity (%)       |
| PM2.5       | PM2.5 concentration (µg/m³) |
| PM10        | PM10 concentration (µg/m³)  |
| AQI         | Air Quality Index value     |
| AQI_Class   | AQI category label          |

---

## Data Collection Platform

Data was collected using the **iHub-Bodhayan** research vehicle developed at IIIT Hyderabad.

### Imaging System

* Insta360 X4 panoramic camera
* Roof-mounted configuration
* Full 360° panoramic capture

### Environmental Sensors

* Nova SDS011

  * PM2.5 measurement
  * PM10 measurement

* AHT10

  * Temperature measurement
  * Relative humidity measurement

All measurements were synchronized using a common timestamping framework to ensure accurate correspondence between imagery and sensor readings.

---

## Dataset Statistics (Full Dataset)

| Property          | Value                   |
| ----------------- | ----------------------- |
| Total Samples     | 33,982                  |
| Collection Days   | 23                      |
| Coverage Distance | ~1000 km                |
| Seasons           | Summer, Monsoon, Winter |
| AQI Range         | 8.4 – 434.7             |
| PM2.5 Range       | 4.2 – 295.1 µg/m³       |
| PM10 Range        | 8.4 – 308.5 µg/m³       |

### Seasonal Distribution

| Season  | Samples | Percentage |
| ------- | ------- | ---------- |
| Summer  | 16,292  | 47.9%      |
| Monsoon | 10,458  | 30.8%      |
| Winter  | 7,232   | 21.3%      |

---

## AQI Categories

Following CPCB standards, AQI values are grouped into the following categories:

| Category     | AQI Range |
| ------------ | --------- |
| Good         | 0–50      |
| Satisfactory | 51–100    |
| Moderate     | 101–200   |
| Poor         | 201–300   |
| Very Poor    | >300      |

---

## Applications

The PAN-AQI dataset can support research in:

* Air Quality Index Classification
* Air Quality Index Regression
* PM2.5 Estimation
* PM10 Estimation
* Vision-Based Environmental Monitoring
* Multimodal Learning
* Panoramic Scene Understanding
* Urban Computing

---

## Example Usage

```python
import pandas as pd
import cv2

# Load metadata
data = pd.read_csv("PAN_AQI.csv")

# Load image
img = cv2.imread("Images/1.jpg")

# Access AQI label
print("AQI:", data["AQI"].iloc[0])

cv2.imshow("Panoramic Image", img)
cv2.waitKey(0)
```

---

## Requirements

The dataset can be used with common machine learning and computer vision frameworks:

* Python 3.x
* PyTorch
* TensorFlow
* OpenCV
* NumPy
* Pandas
* Scikit-learn

---

## License

The sample dataset is provided for academic and research purposes. Please refer to the accompanying license file for usage terms.

---

## Contact

For questions regarding the PAN-AQI dataset, please contact the authors through their institutional affiliations at IIIT Hyderabad.
