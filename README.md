# Data Cleaning with Pandas

## Overview

This repository contains my coursework, Jupyter notebooks, exercises, and notes from the **Data Cleaning with Pandas** course offered through **Anaconda Learning**.

The purpose of this repository is to develop and reinforce practical data-cleaning skills using Python and Pandas. The focus is on understanding how to identify, investigate, and resolve common data-quality issues before performing exploratory data analysis (EDA), statistical modeling, or machine learning.

This repository also serves as a personal reference for data-cleaning techniques and workflows.

## Learning Objectives

The primary objectives are to develop proficiency in:

- Inspecting and understanding dataset structure.
- Identifying and handling missing values.
- Detecting duplicate records.
- Identifying inconsistent data types.
- Converting and standardizing data formats.
- Cleaning and manipulating string data.
- Identifying potential outliers and invalid values.
- Applying appropriate data-cleaning techniques.
- Validating datasets after cleaning.
- Documenting data-cleaning decisions to support reproducibility.

These are general learning objectives; the specific topics covered will depend on the course exercises.

## Development Environment

| Component | Technology |
|---|---|
| Programming Language | Python 3.12 |
| Environment Manager | Conda |
| Notebook Environment | JupyterLab |
| Primary Library | Pandas |
| Course Provider | Anaconda Learning |
| Version Control | Git / GitHub |

Additional libraries may be introduced as the coursework progresses.

## Environment Setup

### 1. Create a Conda Environment

Create a dedicated Conda environment using Python 3.12:

```bash
conda create -n data-cleaning-pandas python=3.12
```

Activate the environment:

```bash
conda activate data-cleaning-pandas
```

### 2. Install Dependencies

Install Pandas, JupyterLab, and the Jupyter kernel package using Conda:

```bash
conda install -c conda-forge pandas jupyterlab ipykernel
```

### 3. Register the Jupyter Kernel

Register the environment so it can be selected within JupyterLab:

```bash
python -m ipykernel install --user \
    --name data-cleaning-pandas \
    --display-name "Python (Data Cleaning with Pandas)"
```

### 4. Launch JupyterLab

From the repository directory, run:

```bash
jupyter lab
```

Select the **Python (Data Cleaning with Pandas)** kernel when opening notebooks.

### 5. Verify the Environment

Run the following in a notebook cell:

```python
import sys
import pandas as pd

print("Python:", sys.version)
print("Python executable:", sys.executable)
print("Pandas version:", pd.__version__)
```

Verify that the Python executable points to the intended Conda environment rather than the system Python installation.

## Repository Organization

The following is a suggested structure that can be adjusted as the course progresses.

```text
data-cleaning-pandas/
│
├── notebooks/
│   └── .gitkeep
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notes/
│   └── .gitkeep
│
├── README.md
├── environment.yml
└── .gitignore
```

### Directory Descriptions

| Directory | Purpose |
|---|---|
| `notebooks/` | Course exercises and Jupyter notebooks |
| `data/raw/` | Original datasets before cleaning |
| `data/processed/` | Cleaned or transformed datasets |
| `notes/` | Course notes, explanations, and reference material |

Original datasets should remain unchanged whenever possible. Cleaned datasets should be saved separately to preserve the source data.

## Data Cleaning Workflow

A general data-cleaning workflow consists of the following stages.

### 1. Data Inspection

Understand the structure and contents of the dataset.

Common Pandas operations include:

```python
df.head()
df.info()
df.shape
df.dtypes
df.describe()
```

### 2. Missing Data Assessment

Identify missing values and determine their extent.

```python
df.isna().sum()
df.isna().mean() * 100
```

The second expression calculates the percentage of missing values in each column.

### 3. Duplicate Detection

Identify duplicate records.

```python
df.duplicated().sum()
```

Determine whether duplicate records represent data-quality issues before removing them.

### 4. Data Type Validation

Review column data types and identify values requiring conversion.

```python
df.dtypes
```

### 5. Data Cleaning and Transformation

Apply appropriate cleaning techniques based on the characteristics of the dataset.

Potential operations include:

- Handling missing values.
- Removing confirmed duplicate records.
- Correcting inconsistent data types.
- Standardizing text and categorical values.
- Correcting invalid or inconsistent records.

### 6. Data Validation

Reinspect the dataset after cleaning to verify that the intended changes were successful.

Document significant transformations and their rationale.

## Notebook Documentation

Each notebook should clearly document:

1. **Objective:** What the exercise is intended to accomplish.
2. **Dataset:** The source and purpose of the data.
3. **Initial Inspection:** Dataset structure and identified quality issues.
4. **Cleaning Operations:** Transformations performed.
5. **Validation:** Checks confirming the results.
6. **Key Takeaways:** Concepts learned and observations.

Markdown cells should explain the reasoning behind important cleaning decisions rather than simply repeating what the code does.

## Environment Reproducibility

Export the Conda environment after installing the required dependencies:

```bash
conda env export --no-builds > environment.yml
```

The exported file may contain a machine-specific `prefix` entry. Remove that entry before committing if present.

To recreate the environment:

```bash
conda env create -f environment.yml
```

Activate the recreated environment using the name defined in the YAML file.

## Version Control

Git is used to track coursework, notebooks, notes, and changes throughout the learning process.

The repository's `.gitignore` should exclude:

- Conda environments and virtual environments.
- Python cache files.
- Jupyter notebook checkpoints.
- IDE configuration files.
- Sensitive configuration files and credentials.
- Large generated datasets and temporary outputs.

Jupyter notebooks, source code, Markdown documentation, and environment configuration files should remain under version control.

## Course Progress

| Topic | Status |
|---|---|
| Dataset inspection and structure | Not started |
| Missing data | Not started |
| Duplicate records | Not started |
| Data type conversions | Not started |
| String and categorical cleaning | Not started |
| Outlier and invalid-value assessment | Not started |
| Data validation | Not started |

*This table is an initial learning tracker, not the official Anaconda Learning course syllabus.*

## References

- [Anaconda](https://www.anaconda.com/)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Python Documentation](https://docs.python.org/3.12/)
- [JupyterLab Documentation](https://jupyterlab.readthedocs.io/)
- [Conda Documentation](https://docs.conda.io/)

## Purpose

This repository is maintained as a personal learning resource to strengthen practical data preparation and analytical skills.

The emphasis is on understanding the techniques, practicing their application, and building reliable, reproducible data-cleaning workflows.
