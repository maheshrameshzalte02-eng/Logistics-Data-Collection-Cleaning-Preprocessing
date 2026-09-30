# Logistics Data Collection, Cleaning & Preprocessing

Python-based data preprocessing and quality assessment on the **DataCo SMART Supply Chain dataset** — covering data cleaning, missing-value treatment, duplicate removal, date processing, outlier detection, feature engineering, normalization, and standardization for logistics analysis.

## Overview

This project focuses on preparing logistics and supply chain data for reliable analysis by applying a structured data preprocessing pipeline. The workflow uses Python, Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn to transform raw logistics data into a clean and analysis-ready dataset.

The analysis begins with data collection and initial inspection, followed by validation of data types, missing values, and duplicate records. Missing numerical and categorical values are handled using appropriate statistical techniques, while duplicate records are removed to improve data consistency.

Logistics-specific preprocessing is also performed by converting order and shipping dates into datetime format and creating a `Delivery_Delay` feature based on actual versus scheduled shipping duration.

Potential outliers are identified using the **Interquartile Range (IQR)** method. Rather than automatically deleting extreme values, they are reviewed because unusually large orders, shipping quantities, costs, or delivery times may represent genuine logistics events.

Finally, selected numerical variables are transformed using **Min-Max Normalization** and **Standardization**, producing a dataset suitable for further exploratory analysis and machine learning.

## Key Results

* Raw logistics data was inspected for **missing values, duplicate records, data types, and statistical inconsistencies**
* Missing numerical values were handled using **median imputation**
* Missing categorical values were handled using **mode imputation**
* Complete duplicate records were removed during preprocessing
* Order and shipping date fields were converted into proper **datetime format**
* A new `Delivery_Delay` feature was created using actual and scheduled shipping duration
* Delivery records were classified as **Late, On Time, or Early**
* Potential outliers were detected using the **IQR method**
* Selected numerical variables were transformed using **Min-Max Normalization**
* Standardized versions of selected numerical variables were created using **StandardScaler**
* The final dataset was validated and exported as a preprocessed CSV file

## Dataset

This project uses the **DataCo SMART Supply Chain for Big Data Analysis** dataset, publicly available on Mendeley Data.

**Dataset:** [Mendeley Data — DataCo SMART Supply Chain Dataset](https://data.mendeley.com/datasets/8gx2fvg2k6/5)

The dataset contains logistics and supply chain information related to orders, products, customers, sales, shipping, delivery, quantities, markets, and regions.

### Dataset File

```text
DataCoSupplyChainDataset.csv
```

The raw CSV is **not included in this repository if it exceeds GitHub's file-size limit**. To reproduce the project, download the dataset from the Mendeley link above and place it in the `data/` folder.

## Tech Stack

* **Python** — Pandas, NumPy
* **Data Visualization** — Matplotlib, Seaborn
* **Data Transformation** — Scikit-learn
* **Development** — Jupyter Notebook, VS Code

## Project Structure

```text
Logistics-Data-Preprocessing/
│
├── data/
│   └── DataCoSupplyChainDataset.csv
│       # Raw dataset — not included if too large
│
├── Logistics_Week2_Preprocessing.ipynb
│   └── Complete preprocessing workflow
│
├── DataCoSupplyChain_Preprocessed.csv
│   └── Cleaned and transformed dataset
│
├── Week_2_Logistics_Data_Preprocessing_Report.docx
│   └── Detailed preprocessing report
│
└── README.md
    └── Project documentation
```

## How to Run

```bash
# Clone the repository
git clone https://github.com/<your-username>/Logistics-Data-Preprocessing.git

# Enter the project directory
cd Logistics-Data-Preprocessing

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# Start Jupyter Notebook
jupyter notebook
```

Download the dataset from:

[DataCo SMART Supply Chain Dataset](https://data.mendeley.com/datasets/8gx2fvg2k6/5)

Then place it here:

```text
data/DataCoSupplyChainDataset.csv
```

Open:

```text
Logistics_Week2_Preprocessing.ipynb
```

and run the notebook cells.

## Methodology

1. **Data Collection** — The DataCo SMART Supply Chain dataset is collected from the public Mendeley Data repository.
2. **Initial Inspection** — Dataset shape, columns, data types, descriptive statistics, missing values, and duplicates are examined.
3. **Data Cleaning** — Duplicate records are removed and missing values are handled according to variable type.
4. **Missing Value Treatment** — Median imputation is used for numerical variables and mode imputation for categorical variables.
5. **Date Processing** — Order and shipping date columns are converted to datetime format.
6. **Feature Engineering** — `Delivery_Delay` is calculated by comparing actual and scheduled shipping duration.
7. **Delivery Classification** — Delivery records are categorized as `Late`, `On Time`, or `Early`.
8. **Outlier Detection** — The IQR method is applied to selected numerical and logistics variables.
9. **Normalization** — Min-Max Scaling transforms selected numerical variables to a 0–1 range.
10. **Standardization** — StandardScaler creates standardized versions of selected numerical variables.
11. **Validation** — The final dataset is checked for remaining missing values, duplicates, dimensions, and data consistency.
12. **Export** — The processed data is saved as `DataCoSupplyChain_Preprocessed.csv`.

## Outlier Detection

The **Interquartile Range (IQR)** method is used to identify potential outliers.

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR

Upper Bound = Q3 + 1.5 × IQR
```

Outliers are identified rather than automatically removed because extreme logistics values can represent legitimate business events.

## Data Transformation

### Min-Max Normalization

```text
X' = (X - Xmin) / (Xmax - Xmin)
```

This scales selected numerical variables between 0 and 1.

### Standardization

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
```

Standardization transforms variables toward a mean of 0 and standard deviation of 1.

## Output

The preprocessing pipeline generates:

```text
DataCoSupplyChain_Preprocessed.csv
```

The output contains the cleaned dataset along with engineered, normalized, and standardized features.

## Business Relevance

The processed dataset can be used for:

* Delivery performance analysis
* Supply chain KPI development
* Shipping and order analysis
* Regional logistics analysis
* Data-quality monitoring
* Outlier investigation
* Exploratory data analysis
* Future predictive analytics

Reliable preprocessing helps reduce the risk of misleading results caused by incomplete, duplicated, inconsistent, or improperly scaled data.

## Limitations

* The raw dataset may need to be downloaded separately because of GitHub's file-size restrictions.
* Outliers are detected but not automatically removed because some extreme logistics observations may be legitimate.
* `Delivery_Delay` uses actual shipping duration and is therefore intended for descriptive/preprocessing analysis rather than a pre-dispatch prediction feature.
* For future machine-learning models, scaling should be fitted on training data only to avoid data leakage.

## Author

**Mahesh Zalte** — [LinkedIn](https://linkedin.com/in/mahesh-zalte-783091268)

Bachelor of Computer Science Graduate | MCA Student

### Skills

```text
Python | SQL | Pandas | NumPy | Power BI | Excel
Data Cleaning | Data Preprocessing | EDA
Matplotlib | Seaborn | Scikit-learn
Jupyter Notebook | VS Code
```

## Project Status

**Completed — Week 2: Data Collection, Cleaning & Preprocessing**
