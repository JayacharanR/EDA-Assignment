# Exploratory Data Analysis Assignments in Python

Python implementations of nine Exploratory Data Analysis assignments, converted from the original R solutions and organized in a single Jupyter notebook. Each assignment includes its questions, a short explanation, Python code, and saved results.

**Name:** Jayacharan R  
**Registration Number:** 23BDS0065  
**Course:** BCSE331P - Exploratory Data Analysis  
**Semester:** Fall 2026-27

## Assignments

| Assignment | Topic | Main operations |
| --- | --- | --- |
| 1 | Merging and Data Transformation | Append and concatenate data frames; inner, left, right, and outer joins; min-max normalization, Z-scores, and decimal scaling |
| 2 | Data Import and Basic Statistical Analysis | Inspect data, handle missing values, remove duplicates, transform columns, and calculate descriptive statistics |
| 3 | Data Cleaning and Univariate Analysis | Check data types, detect outliers, compare imputation methods, and visualize individual variables |
| 4 | Bivariate Analysis | Contingency tables, grouped comparisons, scatter plots, density plots, box plots, and correlation displays |
| 5 | Multivariate Analysis | Encode variables using color, shape, and size; create facets, pairs plots, and parallel coordinates |
| 6 | Time Series Analysis | Explore AirPassengers, perform multiplicative decomposition, inspect ACF and PACF, fit seasonal ARIMA, and forecast 12 months |
| 7 | One, Two and Multiple Variable Analysis | Frequency distributions, grouped statistics, Pearson and Spearman correlations, regression plots, and heatmaps |
| 8 | K-Means and Hierarchical Clustering | Prepare numeric features, standardize data, inspect the WCSS elbow curve, and apply K-means and Ward clustering |
| 9 | Principal Component Analysis | Clean and standardize numeric data, calculate principal components, and visualize explained variance, loadings, and scores |

## Files

| File | Description |
| --- | --- |
| [Python notebook](23BDS0065_EDA_Assignments_1_to_9_Python.ipynb) | All nine assignments with executable Python cells and saved outputs |
| [Assignment PDF](23BDS0065_EDA_Assignments_1_to_9.pdf) | Questions, explanations, code, tables, and plots exported from the notebook |
| [Faculty explanation transcript](23BDS0065_EDA_Faculty_Explanation_Transcript.pdf) | Speaking notes for each assignment and likely faculty questions and answers |
| [Assignments with explanation transcript](23BDS0065_EDA_Assignments_With_Explanation_Transcript.pdf) | Combined PDF with the speaking transcript before each assignment's questions and code, followed by faculty Q&A |

## Datasets

### Horse Colic

Assignments 2-5 and 7-9 use the supplied `horse_colic_data.csv`, containing **110 records and 28 columns**. The dataset includes clinical measurements, categorical observations, and outcomes.

The CSV is embedded in the notebook, so the original local file path is not required. Calling `load_horse()` returns a fresh copy for each assignment. To use another compatible CSV, pass its path to `load_horse("path/to/horse_colic_data.csv")` in the relevant loading cell. Independent cleaning examples use separate copies of the data.

### AirPassengers

Assignment 6 uses **144 monthly observations from January 1949 to December 1960**, measured in thousands of passengers. These values are included directly in the notebook.

## Setup

The notebook was executed using Python 3.12. Create and activate a virtual environment before installing dependencies.

```bash
python -m venv .venv
```

On Linux or macOS:

```bash
source .venv/bin/activate
```

On Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Install JupyterLab and the required analysis packages:

```bash
python -m pip install jupyterlab ipykernel numpy pandas matplotlib seaborn scipy scikit-learn statsmodels adjustText
```

For optional Excel imports, also install `openpyxl` for `.xlsx` files or `xlrd` for `.xls` files.

## Run the Notebook

Launch JupyterLab from the folder containing the notebook:

```bash
jupyter lab
```

Open `23BDS0065_EDA_Assignments_1_to_9_Python.ipynb`, select the Python environment containing the installed packages, and run all cells from top to bottom. The setup cells define imports, the dataset loader, and shared helper functions used by later assignments.

Saved outputs are included for reading without rerunning the analysis. The notebook contains **47 executed code cells and 55 plot outputs**.

## Interpretation Notes

- Sample variance and standard deviation use `ddof=1` to match the corresponding R calculations.
- Plots and statistics can use different subsets of records depending on which variables have missing values.
- Clustering uses a fixed random seed. Cluster labels are arbitrary, and the retained three-cluster solution is an exploratory choice.
- The PCA workflow follows the source solution: it retains the numeric hospital identifier and leaves only eight complete numeric records. These choices limit interpretation.
- The time series forecast uses SARIMA `(0, 1, 1)(0, 1, 1, 12)` and includes 95% prediction intervals. Held-out forecast accuracy is not evaluated.
- Observed associations and clusters are descriptive findings rather than validated clinical predictions.
