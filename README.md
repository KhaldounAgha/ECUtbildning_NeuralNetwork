# Data Preprocessing and Cleaning Script
This repository contains a Python script for data preprocessing and cleaning, including normalization, log transformation, and data cleaning operations. The script is designed to handle various data preprocessing tasks and clean datasets efficiently.
Features
1. Normalization
  •	L1 Normalization (Manhattan Norm): Normalizes the data using the L1 norm.
  •	L2 Normalization (Euclidean Norm): Normalizes the data using the L2 norm.
2. Log Transformation
  •	Applies a log transformation to the data using log(x + 1) to handle skewed distributions and reduce the influence of extreme values.
3. Data Cleaning
  •	DataCleaner Class: A comprehensive class for cleaning datasets, including:
      o	Handling missing values.
      o	Removing duplicates.
      o	Stripping whitespace from string columns.
      o	Cleaning and standardizing column values.
      o	Processing and standardizing date columns.
Usage
Normalization and Log Transformation
python
Copy
import numpy as np

## L1 Normalization
X_Normalized_L1 = X / np.sum(np.abs(X))

## L2 Normalization
X_Normalized_L2 = X / np.sqrt(np.sum((X)**2))

## Log Transformation
X_Log1_Transformed = np.log1p(X)
Data Cleaning
python
Copy
## Initialize the DataCleaner with the directory containing your data
cleaner = DataCleaner(dir=r"path_to_your_directory")

## Perform data cleaning steps
  cleaner.directory_path()
  cleaner.logging_path()
  cleaner.configure_logging()
  cleaner.dataset_path()
  cleaner.read_data()
  cleaner.rename_columns()
  cleaner.dataset_info()

  cleaner.drop_duplicated()
  cleaner.drop_missing()
  cleaner.strip_columns()
  cleaner.clean_values()
  cleaner.clean_date()
  cleaner.process_date_column()

## Save the cleaned data to a CSV file
output_dir = r"path_to_output_directory"
output_file = "cleaned_students_performance.csv"
output_path = os.path.join(output_dir, output_file)
cleaner.df.to_csv(path_or_buf=output_path, mode="w", index=False)
Requirements
  •	Python 3.x
  •	NumPy
  •	Pandas
  •	Scikit-learn
  •	Logging
  •	Datetime
Installation
1.	Clone the repository:
bash
Copy
git clone https://github.com/yourusername/data-preprocessing-cleaning.git
2.	Install the required packages:
bash
Copy
pip install numpy pandas scikit-learn
Example
An example dataset (Students_Performance.csv) is provided in the repository. You can use this dataset to test the script.
