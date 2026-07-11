Zomato Data Analysis
A data cleaning and preparation pipeline for the Zomato Bangalore restaurants dataset, built with Python and pandas. The project takes the raw, messy Zomato CSV export and transforms it into an analysis-ready dataset.

Overview
The raw Zomato dataset contains inconsistent formatting, missing values, and columns that aren't useful for analysis (URLs, phone numbers, review text, etc.). This project cleans and standardizes the data so it's ready for exploratory data analysis or visualization.

Key cleaning steps:

Dropped irrelevant columns (url, phone, rest_type, dish_liked, reviews_list, menu_item, listed_in(city))
Renamed columns for clarity (e.g. approx_cost(for two people) → two_people_cost, rate → rating)
Removed rows with missing location, cuisines, or cost values
Converted two_people_cost from a comma-formatted string to a numeric type, then derived a cost_per_person field
Parsed the rating column (handling values like "NEW" and "-") into a clean float, filling any remaining missing ratings with the column mean
Exported the cleaned dataset to zomato_data_analysis.csv
Repository Structure
Zomato_data_analysis/
├── data/            # Raw and/or cleaned CSV data
├── notebooks/        # Jupyter notebook version of the cleaning pipeline
├── python/            # Standalone .py script version of the pipeline
└── requirement.txt   # Python dependencies
Getting Started
Prerequisites
Python 3.8+
pip
Installation
git clone https://github.com/rajitgupta99/Zomato_data_analysis.git
cd Zomato_data_analysis
pip install -r requirement.txt
Usage
Place the raw zomato.csv file in the same directory as the script/notebook, then run either:

Jupyter Notebook

jupyter notebook notebooks/zomato_cleaning_notebook.ipynb
Python script

python python/zomato_cleaning.py
Both will output a cleaned file, zomato_data_analysis.csv, ready for further analysis or visualization.

Dependencies
pandas — data manipulation and cleaning
numpy — numerical operations
See requirement.txt for the full list.

Dataset
This project expects the Zomato Bangalore Restaurants dataset (zomato.csv), commonly found on Kaggle. The raw file is not included in this repo due to size — download it separately and place it in the data/ folder.

License
This project is open source and available for personal and educational use.
