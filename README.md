# OceanEmbed

### Satellite Embedding-Based Deep Learning Framework for Reconstruction of Subsurface Ocean Temperature from Surface Satellite Observations

OceanEmbed is a Python-based proof-of-concept that uses surface ocean observations and a PyTorch convolutional encoder-decoder model to reconstruct subsurface ocean temperature fields across multiple depths.

The project is developed as a prototype for **Smart India Hackathon – Problem Statement ID-26066**, associated with the Ministry of Earth Sciences (MoES) and INCOIS.

> **Note:** This repository contains a proof-of-concept implementation. The current model and evaluation results should not be interpreted as production-validated oceanographic predictions.

---

## 🌊 Problem

Direct measurement of subsurface ocean temperature is difficult because observations from instruments such as Argo floats are spatially and temporally sparse.

At the same time, satellite observations provide extensive surface-level information about the ocean.

The objective of OceanEmbed is to explore whether surface ocean information can be transformed into a spatial representation that helps reconstruct the temperature structure of the ocean below the surface.

---

## 💡 Proposed Approach

OceanEmbed uses a deep-learning pipeline that:

1. Obtains oceanographic data from the **Copernicus Marine / GLORYS** reanalysis dataset.
2. Extracts surface-level ocean features.
3. Preprocesses the data onto a fixed spatial grid.
4. Feeds the surface features into a PyTorch convolutional encoder-decoder.
5. Learns a compact latent representation of the surface ocean state.
6. Reconstructs temperature fields at multiple subsurface depths.
7. Visualizes predictions and spatial error statistics through an interactive Streamlit dashboard.

---

## 🔄 System Workflow

```text
        GLORYS / Ocean Data
                │
                ▼
        Data Acquisition
                │
                ▼
       NetCDF Preprocessing
                │
                ▼
      Surface Feature Extraction
                │
                ▼
       7-Channel Input Grid
                │
                ▼
       PyTorch Encoder
                │
                ▼
        Latent Embedding
                │
                ▼
       Decoder / Upsampling
                │
                ▼
   15-Depth Temperature Fields
                │
                ▼
      Prediction & Evaluation
                │
                ▼
       Streamlit Dashboard