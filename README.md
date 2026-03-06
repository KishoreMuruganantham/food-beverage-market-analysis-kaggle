# Food & Beverage Market Analysis

A data analysis mini project focused on product launch trends in the food and beverage market. The repository includes a Kaggle-ready Jupyter notebook, the source datasets, exported summary tables, and the original assignment documents.

## Project Overview

This project analyzes historical product launch data to answer business questions around:

- flavor diversity and flavor parsing
- market subcategory launch trends over time
- flavor-group performance, especially Fruit launches by quarter
- positioning analysis for Convenience and Ethical themes
- monthly, quarterly, and yearly launch aggregation
- targeted filtering for Canada, 2013, Energy Drinks, and Ethical Packaging
- hypothesis testing for the top positioning groups in 2013
- export-ready datasets and summary tables

The notebook is designed to run from top to bottom in Kaggle and includes:

- structured markdown explanations
- data cleaning and preprocessing
- charts and statistical analysis
- business insights
- CSV and Excel exports

## Main Files

- `food-beverage-market-analysis.ipynb`: Final Kaggle-ready analysis notebook
- `Product Launch Dataset.csv`: Main product launch dataset
- `Flavor Classification Dataset.csv`: Flavor to flavor-group mapping file
- `Positioning Category Mapping Dataset.csv`: Positioning to positioning-group mapping file
- `Outputs/`: Exported cleaned datasets and summary tables
- `F_B Market Analysis.pdf`: Assignment brief
- `F_B Market Analysis.docx`: Assignment document source

## Notebook Workflow

The notebook is organized into these sections:

1. Introduction
2. Data Loading and Initial Exploration
3. Data Cleaning and Standardization
4. Flavor Column Handling
5. Market Subcategory Trend Analysis
6. Flavor Group Analysis
7. Positioning Analysis
8. Data Aggregation
9. Filtering, Subsetting, and Hypothesis Testing
10. Business Insights and Export Outputs

## Kaggle Dataset Paths

The notebook uses these Kaggle input paths:

```text
/kaggle/input/datasets/mkishore129/assignment5/Product Launch Dataset.csv
/kaggle/input/datasets/mkishore129/assignment5/Flavor Classification Dataset.csv
/kaggle/input/datasets/mkishore129/assignment5/Positioning Category Mapping Dataset.csv
```

## Tools and Libraries

The analysis uses:

- pandas
- numpy
- seaborn
- matplotlib
- scipy
- pathlib
- IPython.display

## Key Data Engineering Decisions

### Robust file loading

The notebook reads CSV files using multiple encodings to handle non-UTF8 source files. It also tries multiple separators and skips malformed rows when necessary.

### Flavor parsing

The `flavor` column contains two levels of separators:

- `||` separates product variants
- `;` separates multiple flavors within a variant

The notebook first explodes variants and then explodes individual flavors, producing a normalized long-format flavor table.

### Positioning parsing

The positioning field can contain multiple labels. The notebook uses the mapping table to preserve labels that include commas, which avoids splitting valid labels such as `Functional, not specified` into incorrect fragments.

### Normalization

Text normalization handles:

- inconsistent whitespace
- quote cleanup
- inconsistent dash characters
- missing value markers such as `NA`, `null`, and related variants

## Outputs Produced

Running the notebook produces these exports in `Outputs/` or `outputs/` depending on environment case sensitivity:

- `product_launch_cleaned.csv`
- `processed_flavor_dataset.csv`
- `monthly_launch_summary.csv`
- `quarterly_launch_summary.csv`
- `yearly_launch_summary.csv`
- `canada_2013_energy_drinks_ethical_packaging.csv`
- `market_analysis_summaries.xlsx`

## How to Run

### Kaggle

1. Upload or attach the datasets to Kaggle.
2. Open `food-beverage-market-analysis.ipynb`.
3. Ensure the dataset paths match the Kaggle input mount.
4. Run all cells from top to bottom.

### Local

1. Create a Python environment.
2. Install dependencies:

```bash
pip install pandas numpy seaborn matplotlib scipy openpyxl xlsxwriter jupyter
```

3. Update the dataset paths if you are not using Kaggle.
4. Run the notebook in Jupyter or VS Code.

## Repository Structure

```text
.
|-- food-beverage-market-analysis.ipynb
|-- Product Launch Dataset.csv
|-- Flavor Classification Dataset.csv
|-- Positioning Category Mapping Dataset.csv
|-- Outputs/
|   |-- product_launch_cleaned.csv
|   |-- processed_flavor_dataset.csv
|   |-- monthly_launch_summary.csv
|   |-- quarterly_launch_summary.csv
|   |-- yearly_launch_summary.csv
|   `-- canada_2013_energy_drinks_ethical_packaging.csv
|-- F_B Market Analysis.pdf
|-- F_B Market Analysis.docx
|-- README.md
`-- .gitignore
```

## Business Questions Covered

- Which market subcategories are gaining or losing momentum over time?
- Which subcategory has the widest flavor variety?
- How are Fruit-flavor launches changing quarter by quarter?
- How common are Convenience and Ethical positioning claims?
- What do monthly, quarterly, and yearly launch summaries show?
- Which flavors were most geographically widespread in 2013?
- Are the top positioning groups in 2013 statistically different?

## Notes

- The notebook was prepared to be executable in Kaggle.
- Source files may contain Windows-encoded characters, so the notebook includes defensive CSV loading logic.
- Some environments may show unresolved import warnings locally even when the notebook runs correctly in Kaggle.

## Author

Prepared as a Food & Beverage Market Analysis assignment submission.
