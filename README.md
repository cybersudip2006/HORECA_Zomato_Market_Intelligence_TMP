# HORECA Zomato Market Intelligence – Exploratory Data Analysis

## Project overview
This project analyses the supplied Zomato menu/restaurant dataset to support three HORECA launch decisions: **cuisine category**, **city/neighbourhood**, and **dining vs delivery channel**. The workflow is descriptive and diagnostic EDA, not a predictive machine-learning model.

## Problem statement
A new food entrepreneur needs data-backed market intelligence to identify a cuisine opportunity, a city/location with demand relative to competition, and the service channel that best matches observed customer ratings and engagement.

## Repository structure
```text
HORECA_Zomato_Market_Intelligence_TMP/
├── data/
│   ├── Zomato Dataset.csv
│   └── zomato_dataset_data_description.xlsx
├── notebooks/
│   └── HORECA_Zomato_EDA.ipynb
├── presentation/
│   └── HORECA_Zomato_Insights.pptx
├── outputs/
│   ├── analysis_summary.json
│   └── figures/
├── README.md
├── requirements.txt
└── .gitignore
```

## Dataset and analytical unit
- 123,657 menu-item rows, 26 columns.
- 914 unique restaurant outlets using restaurant name + city + place as the outlet key.
- 48 cuisine labels and 17 city labels; 13 city labels have at least 20 unique restaurants and are used for macro-city comparisons.
- Menu prices are analysed at item level. Restaurant ratings, total votes and channel metrics are aggregated once per outlet to avoid counting a restaurant repeatedly for every menu item. Cuisine comparisons use outlet-cuisine pairs.

## Methods used
- **Univariate EDA:** descriptive statistics, histograms, category frequency/count plots, price distribution.
- **Bivariate EDA:** dining vs delivery ratings, price vs rating, ratings vs votes, and correlation.
- **Multivariate EDA:** cuisine performance vs demand vs outlet count vs price; city rating vs demand vs supply; neighbourhood comparisons.
- **Geographical analysis:** city and place-level aggregation.
- **Outlier analysis:** IQR method for menu prices.
- **Statistical test:** paired t-test for the mean difference between restaurant dining and delivery ratings.
- **Temporal analysis:** not possible because the supplied data dictionary includes no date/time field.

## Key findings (from the supplied dataset)
- **Cuisine:** Desserts are the stronger mainstream option (about 90 outlets, average rating about 3.93, median total votes 185, median item price ₹220). Kebab is a smaller niche candidate (12 outlets, average rating about 3.90, median total votes 422.5, median item price ₹240); the small sample needs local validation.
- **City:** Ahmedabad is a demand-led underserved candidate (74 outlets, average rating about 3.85, median votes 186, 19 outlets rated at least 4.0). Pune is a viable alternative with 60 outlets, average rating about 3.89 and median votes 179.5. Mumbai has the highest mean menu-item price among the major-city candidates, about ₹304.
- **Neighbourhood:** C G Road (Ahmedabad) has four outlets in this dataset, an average rating about 4.04 and median total votes about 410.5. The dataset includes one dessert outlet there with about 3.95 rating and 363 votes. These are small-sample signals, not a guarantee.
- **Channel:** Mean restaurant delivery rating is about 3.96 vs dining about 3.80. Delivery rating is higher at 563/914 outlets. However, median delivery votes are zero and non-zero delivery votes occur at fewer outlets (314 vs 553 for dining). Recommendation: delivery-friendly with a compact dine-in option; validate actual order economics before going delivery-only.
- **Data quality:** no missing cells were found in the supplied CSV. However, `Is_Bestseller` is constant at 1 across all rows and should not be used as a discriminator; use `Best_Seller` text tags. Price is right-skewed: median ₹208.57; the IQR upper fence is ₹552.50 and about 4.4% of items are above it.

## Business recommendation
Use Desserts as the mainstream category to test, with a delivery-friendly menu and compact dine-in capability. Shortlist Ahmedabad and test micro-markets such as C G Road; compare with Pune as a second-city benchmark. Use Kebab as a separate small-scale niche pilot, rather than treating its 12-outlet sample as conclusive.

## How to run
1. Install Python 3.10+ (or a current compatible Python version).
2. Open a terminal in the repository root.
3. Install dependencies: `pip install -r requirements.txt`.
4. Launch Jupyter: `jupyter notebook`.
5. Open `notebooks/HORECA_Zomato_EDA.ipynb` and run all cells from top to bottom.

## Important limitations
This dataset contains ratings, votes and listed menu prices, not actual order revenue, operating cost, rent, platform commission, gross margin or customer acquisition cost. Votes are not equivalent to sales. It has no timestamp, so trend/seasonality analysis is not possible. The analysis therefore identifies **market opportunities to validate**, not proven profitability.

## Submission note
The college instruction requires the repository name format `HORECA_ProjectName_TMP`. Suggested name: `HORECA_Zomato_Market_Intelligence_TMP`. Include the original dataset and data description file so the analysis can be reproduced.
