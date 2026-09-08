# DNS Data Exfiltration Challenge

This repository contains tools and data for a machine learning challenge focused on detecting malicious activity in DNS traffic. The goal is to identify DNS-based data exfiltration and covert command-and-control (C2) tunneling.

## Overview

DNS is a critical service that is often allowed through firewalls, making it a prime target for adversaries to encode and exfiltrate sensitive information stealthily. This project utilizes the **CIC-Bell-DNS-EXF-2021** dataset, developed in collaboration with Bell Canada Cyber Threat Intelligence (CTI), to build models that can detect these "low-and-slow" attacks.

The current implementation focuses on using **stateless features** to differentiate between normal DNS traffic and malicious exfiltration attempts.

## Repository Structure

- `Exfiltration_EDA.ipynb`: A Jupyter Notebook containing Exploratory Data Analysis (EDA) to understand the characteristics and distributions of the DNS dataset.
- `Exfiltration_Model.ipynb`: A Jupyter Notebook focused on building, training, and evaluating machine learning models to distinguish between benign and malicious traffic.
- `Exfiltration_Explainability.ipynb`: A Jupyter Notebook dedicated to machine learning explainability, exploring how models make their predictions and which features are most influential.
- `data/`: Contains the datasets used for training and evaluation.
    - `Exfil_Data.csv`: A sample/subset of the DNS exfiltration dataset.
- `environment_core.yml`: A Conda environment specification file to ensure reproducible research environments.

## Dataset Information

The dataset used is the [CIC-Bell-DNS-EXF-2021](https://www.unb.ca/cic/datasets/dns-exf-2021.html). It provides features extracted from DNS queries, including:
- Subdomain characteristics (length, entropy, special characters)
- Label information (count, max, average)
- Character composition (upper, lower, numeric)
- FQDN properties

## Getting Started

### Prerequisites

You will need [Conda](https://docs.conda.io/en/latest/) installed on your system.

### Environment Setup

To create the necessary environment, run the following commands:

```bash
conda env create -f environment_core.yml
conda activate dsd_converge_2025_core
```

### Running the Analysis

Once the environment is set up, you can launch JupyterLab to explore the notebooks:

```bash
jupyter lab
```

Then, open one of the notebooks (e.g., `Exfiltration_EDA.ipynb`) to begin the analysis.
