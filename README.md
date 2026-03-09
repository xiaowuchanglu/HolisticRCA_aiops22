# HolisticRCA (AIOps'22) Reproduction

This repository reproduces the paper:

**Holistic Root Cause Analysis for Microservice Systems (AIOps 2022)**

The goal of this project is to reproduce the **HolisticRCA pipeline**, including:

- Observability data preprocessing
- Feature extraction from **logs / metrics / traces**
- resource entity relation graph construction
- Training the **HolisticRCA model**

The repository extends the original implementation with a **complete data processing pipeline** for AIOps datasets.

---

# Project Structure

```
HolisticRCA_aiops22/
│
├─ code/
│
│  ├─ data_filter/                # Data preprocessing pipeline
│  │
│  │  ├─ 1.extractLogTemplate_aiops22.ipynb
│  │  ├─ 2.extractIstioWords_aiops22.ipynb
│  │
│  │  ├─ 3-1.extractLogFeature_aiops22.ipynb
│  │  ├─ 3-2.extractMetricFeature_aiops22.ipynb
│  │  ├─ 3-3.extractTraceFeature_aiops22.ipynb
│  │  ├─ 3-4.extractTopology_aiops22.ipynb
│  │
│  │  ├─ 4.LabelsGenerator_aiops22.ipynb
│  │
│  │  ├─ 5-1.LogGenerator_aiops22.ipynb
│  │  ├─ 5-2.TraceGenerator_aiops22.ipynb
│  │  ├─ 5-3.MetricGenerator_aiops22.ipynb
│  │  ├─ 5-4.TopologyGenerator_aiops22.ipynb
│  │
│  │  └─ 6.dataGenerator_aiops22.ipynb
│  │
│  └─ HolisticRCA/
│     └─ trainer/
│        └─ rca_trainer.ipynb     # Model training
│
├─ data/
│  ├─ raw/                       # Raw observability data
│  ├─ interim/                   # Intermediate feature files
│  └─ processed/                 # Final training dataset
│
└─ README.md
```

---

# Pipeline Overview

The full reproduction pipeline consists of **three stages**:

1️⃣ **Log preprocessing**

Extract log templates and domain-specific keywords.

2️⃣ **Feature extraction**

Extract features from three observability sources:

- Logs
- Metrics
- Traces

Additionally, construct the **resource entity relation graph graph**.

3️⃣ **Dataset construction**

Generate the final training dataset used by HolisticRCA.

4️⃣ **Model training**

Train the HolisticRCA model for root cause analysis.

---

# Data Processing Pipeline

The notebooks in `code/data_filter` should be executed in the following order.

---

## Step 1 — Extract Log Templates

```
1.extractLogTemplate_aiops22.ipynb
```

---

## Step 2 — Extract Istio Keywords

```
2.extractIstioWords_aiops22.ipynb
```



---

## Step 3 — Feature Extraction

### Log Features

```
3-1.extractLogFeature_aiops22.ipynb
```



---

### Metric Features

```
3-2.extractMetricFeature_aiops22.ipynb
```


---

### Trace Features

```
3-3.extractTraceFeature_aiops22.ipynb
```


---

### resource entity relation graph

```
3-4.extractTopology_aiops22.ipynb
```


---

## Step 4 — Label Generation

```
4.LabelsGenerator_aiops22.ipynb
```


---

## Step 5 — Modal Data Generation



```
5-1.LogGenerator_aiops22.ipynb
```


```
5-2.TraceGenerator_aiops22.ipynb
```


```
5-3.MetricGenerator_aiops22.ipynb
```


```
5-4.TopologyGenerator_aiops22.ipynb
```

---

## Step 6 — Final Dataset Construction

```
6.dataGenerator_aiops22.ipynb
```


---

# Model Training

Training is performed using:

```
code/HolisticRCA/trainer/rca_trainer.ipynb
```
---



# Notes

- The repository extends the original HolisticRCA implementation by adding a **complete data preprocessing pipeline**.

---
