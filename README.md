
# Data Analysis Portfolio

Python projects exploring business questions through statistical analysis, product rating, and review ranking.

## Projects

### 1. A/B Testing: Bidding Strategies

Compare purchase performance between control and test groups using descriptive statistics, Shapiro–Wilk and Levene tests, and an independent-samples t-test. Additional exploratory Welch tests compare observation-level Purchase / Click and Purchase / Impression ratios.

- Mean Purchase: 550.89 in the control group versus 582.11 in the test group; no statistically significant difference was detected (p ≈ 0.349). This does not establish equivalence.
- Mean Purchase / Click: 11.59% versus 15.66%; the exploratory Welch test indicates a difference (p ≈ 0.0025).
- Mean Purchase / Impression: 0.558% versus 0.492%; no statistically significant difference was detected at the 5% threshold (p ≈ 0.0557).

The ratios are averages of individual row ratios, not ratios of group totals. The tests assume independent observations; the notebook does not independently establish the randomization or sampling design. Exploratory p-values are reported without adjustment for multiple comparisons and should not be treated as a confirmed business decision.

[View notebook](ab-testing/a-b-testing.ipynb) · [View on Kaggle](https://www.kaggle.com/code/gulsahyesilmen/a-b-testing)

### 2. Product Rating & Review Ranking

Compare a simple average product rating with a time-weighted rating, then select the top 20 reviews using the Wilson Lower Bound of the helpful-vote proportion.

- Simple average rating: 4.5876.
- Time-weighted rating: 4.6987, using weights of 28%, 26%, 24%, and 22% for four review-age groups.
- Visualizations show ratings by review age, the top 20 ranked reviews, and Wilson scores across all reviews.

The weights are analysis choices, not optimized parameters. The time-weighted function assumes all four groups contain valid ratings and weights total 100. Review age follows the dataset's reference date. Wilson scores reflect helpful-vote proportions and uncertainty; they do not establish review authenticity or accuracy. Unvoted reviews receive zero for ranking purposes.

[View notebook](product-rating/rating-products-sorting-reviews.ipynb) · [View on Kaggle](https://www.kaggle.com/code/gulsahyesilmen/rating-products-sorting-reviews)

## Repository Structure

```text
data-analysis-portfolio/
├── README.md
├── ab-testing/
│   └── a-b-testing.ipynb
└── product-rating/
    └── rating-products-sorting-reviews.ipynb
```

## Running the Notebooks

The notebooks were developed in Kaggle. Their current data paths use `/kaggle/input/`.

1. Open the relevant Kaggle notebook and attach the required dataset, if you have access.
2. Alternatively, download the notebook and obtain the data separately, then replace the data-loading paths with your local paths.
3. Restart the kernel and run all cells in order.

Required data:

| Project | File | Notes |
| --- | --- | --- |
| A/B Testing | `ab_testing.xlsx` | Sheets: `Control Group` and `Test Group` |
| Product Rating | `amazon_review.csv` | Includes ratings, review age, and helpful-vote counts |

Datasets are not included. Access may be restricted; follow the original data provider's permissions and terms. Saved notebook outputs allow inspection without rerunning the analysis.

Libraries used by the current notebooks include pandas, NumPy, SciPy, Matplotlib, Seaborn, statsmodels, scikit-learn, and openpyxl. Some imports are retained from the original exploratory work; exact package versions are not pinned here.

## Author

Gülşah Yeşilmen · [Kaggle](https://www.kaggle.com/gulsahyesilmen) · [GitHub](https://github.com/gulsahyesilmen)
