# DDoS Attack Detection on Azure: End-to-End Big Data Pipeline

## Project Overview

This repository contains the complete implementation of a cloud‑based big data processing solution for detecting **SYN flood DDoS attacks** using the CIC‑DDoS2019 dataset. The architecture is built entirely on Microsoft Azure and covers data ingestion, scalable processing, machine learning, cost optimisation, security, and performance monitoring.

The Random Forest classifier achieves **99.99% accuracy** and **F1 score** on the test set, while cost optimisation reduces monthly cloud expenditure from **$441.42 to just $4.58** (99% saving).

## Repository Contents

| File | Description |
|------|-------------|
| `outputs.docx` | Full project report including all screenshots, figures, tables, cost analysis, and references (York St John Harvard style). |
| `New Notebook 2026-05-26 07_26_57.ipynb` | Databricks notebook (PySpark) containing data extraction, pre‑processing (handling Inf/NaN, label encoding, feature assembly), Random Forest training, evaluation, and analytical SQL queries. |

## Dataset

The dataset used is the **CIC‑DDoS2019** SYN flood subset (`Syn.csv`, ~1.75 GiB).  
It is publicly available on Kaggle:  
[https://www.kaggle.com/datasets/rodrigorosasilva/cic-ddos2019-30gb-full-dataset-csv-files](https://www.kaggle.com/datasets/rodrigorosasilva/cic-ddos2019-30gb-full-dataset-csv-files)

> Place the `Syn.csv` file in an Azure Blob Storage container before running the notebook (see setup below).

## Azure Services Used

- **Azure Blob Storage** (Cool tier, LRS) – raw data lake  
- **Azure Data Factory** – automated ingestion from Kaggle to Blob Storage  
- **Azure Databricks** – Apache Spark cluster with auto‑scaling (1–8 workers) and spot instances  
- **Azure Monitor & Log Analytics** – performance monitoring  
- **Azure RBAC** – fine‑grained access control  

## Setup Instructions

1. **Clone the repository**  
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
