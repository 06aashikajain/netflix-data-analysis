# Netflix Data Cleaning Project

## Project Overview

This project cleans and prepares a Netflix titles dataset using Python in a step-by-step Jupyter Notebook. The notebook focuses on inspecting the dataset, identifying data-quality issues, applying cleaning operations, verifying the results, and exporting a cleaned CSV file.

## Project Files

```text
.
├── Netflix_Data_Cleaning_Stepwise_Notebook.ipynb
├── netflix_titles.csv          # Input dataset (provide this file)
├── netflix_cleaned.csv         # Generated output after running the notebook
├── README.md
└── requirements.txt
```

## Requirements

- Python 3.8 or later
- pandas
- NumPy
- Jupyter Notebook (to open and run the notebook)

Install the dependencies:

```bash
pip install -r requirements.txt
```

## Dataset

The notebook expects an input CSV file named `netflix_titles.csv` in the same directory as the notebook.

The dataset should contain the columns referenced in the notebook, including `show_id`, `description`, `type`, `cast`, `listed_in`, `date_added`, `release_year`, `director`, `country`, `rating`, and `duration`.

The input dataset is not included with this notebook. Place the CSV file in the project directory before running the notebook.

## How to Run

1. Download or clone this project.
2. Place `netflix_titles.csv` in the project directory.
3. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

4. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `Netflix_Data_Cleaning_Stepwise_Notebook.ipynb`.
6. Run the notebook cells in order, from top to bottom.

## Data Cleaning Workflow

The notebook performs the following steps:

1. **Import libraries** – imports pandas and NumPy.
2. **Load dataset** – reads `netflix_titles.csv` into a pandas DataFrame.
3. **Dataset overview** – checks the dataset dimensions, column information, and descriptive statistics.
4. **Check missing values** – counts missing values in each column.
5. **Check duplicate rows** – counts duplicate records.
6. **Remove unnecessary columns** – drops `show_id` and `description`.
7. **Rename columns** – renames selected columns for clearer naming:
   - `type` → `content_type`
   - `cast` → `cast_members`
   - `listed_in` → `genres`
   - `date_added` → `date_added_to_netflix`
8. **Remove duplicate records** – removes duplicate rows.
9. **Handle missing values** – fills missing values in `director`, `cast_members`, `country`, `rating`, and `duration` with `Unknown`.
10. **Convert data types** – converts `date_added_to_netflix` to datetime and `release_year` to pandas nullable integer type.
11. **Remove extra spaces** – strips leading and trailing spaces from object-type columns.
12. **Verify cleaned data** – checks the resulting DataFrame information, sample rows, and missing-value counts.
13. **Export cleaned dataset** – writes the cleaned data to `netflix_cleaned.csv`.

The notebook also lists optional enhancements, such as splitting duration, extracting date components, validating ratings, and creating a data-quality report. These are suggestions only; they are not implemented in the current notebook.

## Output

After successfully running the notebook, the cleaned dataset is saved as:

```text
netflix_cleaned.csv
```

The CSV is saved in the current working directory. The export uses `index=False`, so pandas does not add the DataFrame index as an extra column.

## Notes

- Run the notebook cells in order because later steps depend on the DataFrame created earlier.
- Make sure the input CSV filename and column names match what the notebook expects.
- Date values that cannot be parsed are converted to `NaT` because the notebook uses `errors='coerce'`.
- The notebook does not include a separate automated test suite.
