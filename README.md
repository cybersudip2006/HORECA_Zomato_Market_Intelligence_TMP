HORECA Zomato Market Intelligence – EDA

Academic Details
- **College:** Govt. College of Engineering & Ceramic Technology
- **Department:** Information Technology
- **Submitted by:** Sudip Chakraborty
- **Guide:** Arijit Midya
- **Academic Year:** 2026-27

Overview
Exploratory Data Analysis (EDA) on the Zomato restaurant and menu dataset to help plan a new food venture across three areas:
- **Cuisine** selection
- **City and area** selection
- **Dining vs. delivery** strategy

For a past reference repository, see [HORECA_CTT_Sudip_TMP](https://github.com/Sudip-2005/HORECA_CTT_Sudip_TMP).

Dataset Summary
- **123,657** menu items across **26** columns and **914** unique outlets (by restaurant name, city, and area).
- **48** cuisines and **17** cities (**13** cities with 20+ outlets are used for city comparisons).
- Outlet metrics (ratings and votes) are deduplicated per outlet; prices are analyzed at the menu-item level. No missing cells were found, though `Is_Bestseller` is always `1` (use `Best_Seller` text tags instead) and menu prices are right-skewed (median **₹208.57**, IQR upper fence **₹552.50**, ~4.4% above).

Key Findings & Recommendations
- **Cuisine:** **Desserts** are a balanced mainstream option (~90 outlets, ~3.93 avg rating, 185 median votes, ₹220 median price). **Kebab** is a smaller niche option (12 outlets, ~3.90 avg rating, 422.5 median votes, ₹240 median price) worth testing on a small scale.
- **Location:** **Ahmedabad** shows strong demand relative to ratings (74 outlets, ~3.85 avg rating, 186 median votes, 19 outlets rated 4.0+), with **C G Road** as a micro-market to check (small sample: 4 outlets, ~4.04 avg rating). **Pune** is a good secondary city to compare (60 outlets, ~3.89 avg rating, 179.5 median votes). **Mumbai** has the highest mean menu price (~₹304).
- **Channel:** Delivery ratings average higher (**~3.96** vs. **~3.80** dining), though median delivery votes are **0** (non-zero at 314 outlets vs. 553 for dining). Start delivery-friendly with a compact dine-in setup and validate real orders before going delivery-only.

Repository Structure
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

## How to Run

1. Open a terminal in the project folder.
2. Install packages: `pip install -r requirements.txt`
3. Start Jupyter: `jupyter notebook`
4. Open `notebooks/HORECA_Zomato_EDA.ipynb` and run all cells.

## Limitations

The dataset has ratings, votes, and listed prices—not actual sales, rent, commissions, costs, margins, or dates (so time trends aren't possible). Treat these insights as leads to validate in the real market, not guaranteed profit.

```

<FollowUp label="Want me to paste this directly into your README editor on GitHub?" query="Paste this simplified README directly into the README.md editor on GitHub."/>

```
