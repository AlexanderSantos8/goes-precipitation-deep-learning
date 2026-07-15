# Satellite Data Integration and Processing Framework for Neural Network-Based Precipitation Estimation

![GOES-R](https://img.shields.io/badge/Data-GOES--R-blue)
![MRMS](https://img.shields.io/badge/Radar-MRMS-green)
![Python](https://img.shields.io/badge/Language-Python-yellow)
![Machine Learning](https://img.shields.io/badge/Application-Neural%20Networks-red)

## Overview

This project develops an end-to-end meteorological data processing pipeline designed to prepare high-resolution satellite, lightning, and radar observations for **neural network-based precipitation estimation**.

The framework integrates multiple NOAA atmospheric observation systems:

- **GOES-R Advanced Baseline Imager (ABI)** satellite imagery
- **Geostationary Lightning Mapper (GLM)** lightning observations
- **Multi-Radar/Multi-Sensor (MRMS)** precipitation products

The objective is to transform raw meteorological datasets into structured, spatially aligned inputs suitable for deep learning models such as **Convolutional Neural Networks (CNNs)** and **ConvLSTM architectures** for short-term precipitation forecasting.

---

# Research Objectives

Extreme precipitation events create significant challenges for:

- Flood prediction
- Severe weather monitoring
- Agricultural planning
- Emergency response systems

This project focuses on building a reliable preprocessing framework capable of:

1. Retrieving large-scale meteorological datasets
2. Processing satellite and radar observations
3. Performing spatial coordinate transformations
4. Aligning multiple sensor products
5. Creating machine-learning-ready datasets

---

# Data Sources

## GOES-R Advanced Baseline Imager (ABI)

The ABI instrument provides multispectral observations across 16 spectral channels.

This project utilizes five infrared channels:

| Channel | Wavelength | Purpose |
|---|---|---|
| Channel 8 | 6.2 μm | Upper-level water vapor |
| Channel 10 | 7.3 μm | Lower-level atmospheric moisture |
| Channel 11 | 8.4 μm | Cloud-top phase detection |
| Channel 14 | 11.2 μm | Cloud-top and surface temperature |
| Channel 15 | 12.3 μm | Moisture correction and atmospheric characterization |

These channels provide information about:

- Cloud structure
- Atmospheric moisture
- Cloud-top temperature
- Convective development

---

## Geostationary Lightning Mapper (GLM)

GLM provides continuous lightning observations across the Western Hemisphere.

Lightning locations were extracted as spatial coordinates and projected onto satellite grids to study relationships between:

- Lightning density
- Convective cloud development
- Severe precipitation events

---

## Multi-Radar/Multi-Sensor (MRMS)

MRMS combines:

- Ground radar networks
- Satellite observations
- Surface gauges

to generate high-resolution quantitative precipitation estimates (QPE).

MRMS precipitation rates were used as the **ground-truth target variable** for future neural network training.

---

# Data Processing Pipeline
