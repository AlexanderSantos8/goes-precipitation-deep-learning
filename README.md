# Satellite Data Integration and Processing Framework for Neural Network-Based Precipitation Estimation

![GOES-R](https://img.shields.io/badge/Data-GOES--R-blue)
![MRMS](https://img.shields.io/badge/Radar-MRMS-green)
![Python](https://img.shields.io/badge/Language-Python-yellow)
![Machine Learning](https://img.shields.io/badge/Application-Neural%20Networks-red)

## Overview

This project develops an end-to-end meteorological data processing pipeline designed to prepare high-resolution satellite, lightning, and radar observations for neural network-based precipitation estimation.

The framework integrates multiple NOAA atmospheric observation systems:

- **Geostationary Operational Environmental Satellite (GOES-R) Advanced Baseline Imager (ABI)**
- **Geostationary Lightning Mapper (GLM)**
- **Multi-Radar/Multi-Sensor (MRMS) precipitation products**

The primary objective is to transform raw meteorological datasets into structured, spatially aligned inputs suitable for deep learning models, including Convolutional Neural Networks (CNNs) and ConvLSTM architectures for precipitation forecasting.

---

# Research Objectives

Extreme precipitation events create major challenges for:

- Flood prediction
- Severe weather monitoring
- Agricultural planning
- Emergency response systems

This project establishes a reliable preprocessing framework capable of:

1. Acquiring large-scale meteorological datasets
2. Processing satellite and radar observations
3. Performing spatial coordinate transformations
4. Aligning multiple atmospheric sensors
5. Generating machine-learning-ready datasets

---

# Data Sources

## GOES-R Advanced Baseline Imager (ABI)

The ABI instrument provides multispectral observations across 16 spectral channels.

This project uses five infrared channels:

| Channel | Wavelength | Application |
|---|---|---|
| Channel 8 | 6.2 μm | Upper-level water vapor analysis |
| Channel 10 | 7.3 μm | Lower-level atmospheric moisture |
| Channel 11 | 8.4 μm | Cloud-top phase detection |
| Channel 14 | 11.2 μm | Cloud-top and surface temperature |
| Channel 15 | 12.3 μm | Moisture correction and atmospheric characterization |

These measurements provide information about:

- Cloud structure
- Atmospheric moisture
- Cloud-top temperature
- Convective development

---

# Geostationary Lightning Mapper (GLM)

The GLM instrument provides continuous lightning observations across the Western Hemisphere.

Lightning flashes were extracted as spatial coordinates and projected onto satellite grids to analyze relationships between:

- Lightning density
- Convective storm development
- Heavy precipitation events

---

# Multi-Radar/Multi-Sensor (MRMS)

MRMS combines observations from:

- Ground-based radar networks
- Satellites
- Surface gauge measurements

to generate high-resolution Quantitative Precipitation Estimates (QPE).

MRMS precipitation rates serve as the reference target variable for future neural network training.

---

# Data Processing Pipeline

Raw Meteorological Data
|
v
+--------------------------+
| Data Acquisition |
| GOES / GLM / MRMS |
+--------------------------+
|
v
+--------------------------+
| Data Synchronization |
| rclone + Local Storage |
+--------------------------+
|
v
+--------------------------+
| Satellite Processing |
| Radiance Conversion |
| Brightness Temperature |
+--------------------------+
|
v
+--------------------------+
| Spatial Processing |
| Projection Alignment |
| Geographic Cropping |
+--------------------------+
|
v
+--------------------------+
| Dataset Generation |
| Machine Learning Inputs |
+--------------------------+
|
v
+--------------------------+
| Neural Network Models |
| CNN / ConvLSTM |
+--------------------------+



---

# Technologies Used

## Programming

- Python
- NumPy
- Matplotlib
- Scientific computing libraries

## Data Management

- rclone
- NOAA meteorological repositories

## Machine Learning Applications

Future integration:

- Convolutional Neural Networks (CNN)
- ConvLSTM recurrent architectures
- Deep learning precipitation forecasting models

---

# Study Region

## Puerto Rico

Selected research domain:

Latitude:
18.0°N - 18.5°N

Longitude:
-67.2°W - -65.8°W


Puerto Rico was selected because of:

- Frequent tropical precipitation systems
- High-impact rainfall events
- Availability of multi-sensor radar observations

---

# Results and Validation

## Satellite Projection Validation

The GOES ABI full-disk dataset was successfully processed and validated.

The pipeline verified:

- Correct satellite projection geometry
- Geographic boundary accuracy
- Spatial transformation consistency

---

## Lightning Mapping

GLM observations were successfully converted into spatial lightning maps.

The resulting fields provide additional atmospheric features related to:

- Convective intensity
- Storm evolution
- Heavy rainfall potential

---

## Radar Precipitation Validation

Processed precipitation fields were compared with official NOAA MRMS products.

Validation confirmed:

- Accurate georeferencing
- Correct coordinate transformations
- Proper precipitation scaling
- Pixel-level spatial agreement

Validation event:

September 18, 2022
Puerto Rico precipitation event


---

# Repository Structure
Satellite-Precipitation-NN/
│
├── data/
│ └── Meteorological datasets
│
├── scripts/
│ ├── GOES_processing.py
│ ├── GLM_processing.py
│ └── MRMS_processing.py
│
├── notebooks/
│ └── visualization_analysis.ipynb
│
├── figures/
│ ├── satellite_projection.png
│ ├── lightning_maps.png
│ └── precipitation_maps.png
│
├── models/
│ └── neural_network_architecture/
│
└── README.md


---

# Future Work

Future development will focus on:

- Creating machine learning training datasets
- Implementing CNN precipitation estimation models
- Developing ConvLSTM forecasting architectures
- Predicting short-term rainfall intensity
- Evaluating model performance using historical storms

---

# Scientific Contribution

This project establishes a validated framework connecting:

**Remote Sensing + Radar Meteorology + Artificial Intelligence**

By integrating satellite cloud properties, lightning activity, and radar precipitation measurements, this framework creates a foundation for AI-driven high-resolution precipitation forecasting.

---

# References

[1] NOAA/NASA. *GOES-R Series Space Segment*.  
https://www.goesr.gov

[2] National Severe Storms Laboratory. *Multi-Radar/Multi-Sensor (MRMS) System*.  
https://mrms.nssl.noaa.gov

---

# Author

**Alexander Santos**

Applied Mathematics Research Project  
Colorado State University
