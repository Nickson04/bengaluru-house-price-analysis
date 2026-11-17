# Bengaluru House Price Analysis (Practice Project 3)

This is my third data analytics practice project. I clean and analyze the
Bengaluru House Price dataset using Python and pandas, to understand what
drives house prices in the city.

## About the data
The dataset comes from Kaggle https://www.kaggle.com/datasets/amitabhajoy/bengaluru-house-price-data. It has
13,320 listings with the area type, availability, location, size, number of
bathrooms and balconies, total square feet and price. Prices are in lakhs of
rupees.

## What I did

**Cleaning**
- Dropped `society` (41% missing) and filled missing `bath` and `balcony`
  values with the median
- Converted `total_sqft` to numbers, averaging ranges like "2100-2850"
- Extracted the number of bedrooms (`BHK`) from the `size` text
- Created `price_per_sqft`, and turned `availability` into a yes/no column
- Removed outliers: fewer than 300 sqft per bedroom, too many bathrooms
  for the bedrooms, and the lowest and highest 1% of price per sqft
- In total, 1,068 rows (8%) were removed, leaving 12,252

**Analysis and visualization**
- Price distribution, size vs price, bedrooms (BHK) vs price
- Top 10 locations by median price per sqft (locations with at least 15 listings)

## Key findings
- The highest price per sqft was 1,200,000 before cleaning, clearly an error.
  After cleaning, the maximum is 21,250 and the median is 5,294.
- Half of the listings cost between about 4,200 and 6,900 rupees per sqft.
- The most expensive areas per sqft are Benson Town, Rajaji Nagar,
  Malleshwaram, Indira Nagar and Cooke Town.
- Price rises clearly with size, and with bedrooms up to about 4 to 5 BHK.

## What I learned
- One wrong record can distort an average, so I used the median and a
  minimum number of listings per location
- Checking the units of a column (prices are in lakhs) before calculating
- Removing outliers with clear rules, and documenting how many rows were removed
- Restarting the kernel and running all cells to make sure the notebook
  works from top to bottom

## Limitations
- Prices are asking prices, not final sale prices
- Removing the top 1% of price per sqft excludes the most luxurious listings
- The cleaning thresholds are judgment calls

## Files
- `Bengaluru_House_Price_Analysis.ipynb`: the analysis notebook
- `Bengaluru_House_Data.csv`: the dataset (put it in the same folder as the notebook)

## Tools
Python, pandas, NumPy, matplotlib, seaborn, Jupyter Notebook

## Next steps
Build a regression model to predict price and evaluate it with R² and MAE.
