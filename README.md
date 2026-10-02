# 🛒 Consumer Electronics Sales Data Analysis

Exploratory data analysis (EDA) of a consumer electronics sales dataset, with the goal of understanding which customer and product factors are associated with **purchase intent** — and laying the groundwork for a purchase-intent prediction model.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange)
![pandas](https://img.shields.io/badge/pandas-data%20analysis-150458)
![seaborn](https://img.shields.io/badge/seaborn-visualization-4c72b0)

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Project Structure](#-project-structure)
- [Analysis Workflow](#-analysis-workflow)
- [Key Findings](#-key-findings)
- [Getting Started](#-getting-started)
- [Roadmap](#-roadmap)
- [Tech Stack](#-tech-stack)
- [Contributing](#-contributing)

---

## 🔍 Overview

Retailers and manufacturers want to know *who* is likely to buy *what*. This project explores a dataset of 9,000 consumer electronics records covering five product categories and five brands, and investigates how customer demographics, satisfaction, and product pricing relate to whether a customer intends to purchase.

The notebook walks through data loading, cleaning, and univariate, bivariate, and multivariate analysis using `pandas`, `matplotlib`, and `seaborn`.

---

## 📊 Dataset

**File:** `consumer_electronics_sales_data.csv`
**Size:** 9,000 rows × 9 columns — no missing values, no duplicate rows.

| Column | Type | Description |
|---|---|---|
| `ProductID` | int | Unique identifier for each product record |
| `ProductCategory` | categorical | Smartphones, Smart Watches, Tablets, Laptops, Headphones |
| `ProductBrand` | categorical | Apple, Samsung, Sony, HP, Other Brands |
| `ProductPrice` | float | Product price (range ≈ 100 – 3,000) |
| `CustomerAge` | int | Customer age (18 – 69) |
| `CustomerGender` | int (binary) | Encoded gender (0 / 1) |
| `PurchaseFrequency` | int | Number of purchases by the customer (1 – 19) |
| `CustomerSatisfaction` | int | Satisfaction rating (1 – 5) |
| `PurchaseIntent` | int (binary) | **Target variable** — 1 = intends to purchase, 0 = does not (~56.6% positive) |

The categories are well balanced: each product category and each brand accounts for roughly 1,700 – 1,850 records, and the gender split is close to even (4,580 vs. 4,420).

---

## 📁 Project Structure

```
├── consumer_electronics_sales_data.csv                    # Raw dataset
├── Consumer_Electronics_Sales_Data_Analysis_prediction.ipynb   # Analysis notebook
└── README.md
```

---

## 🧪 Analysis Workflow

1. **Data loading & overview** — `head()`, `tail()`, `describe()`, `info()`
2. **Data cleaning** — missing-value check (none found)
3. **Exploratory data analysis**
   - Distribution of customer age
   - Customer satisfaction by product category (boxplot)
   - Purchase frequency by gender
4. **Univariate analysis** — counts by product category and brand
5. **Bivariate analysis**
   - Product price vs. purchase intent
   - Customer satisfaction vs. purchase intent
6. **Multivariate analysis**
   - Pairplot of numeric features colored by purchase intent
   - Correlation heatmap of numeric features

---

## 💡 Key Findings

Correlation of each numeric feature with `PurchaseIntent`:

| Feature | Correlation |
|---|---|
| `CustomerGender` | **+0.50** |
| `CustomerSatisfaction` | **+0.39** |
| `CustomerAge` | **+0.29** |
| `ProductPrice` | −0.02 |
| `PurchaseFrequency` | ≈ 0.00 |

- **Customer demographics and satisfaction are the strongest signals** of purchase intent — higher satisfaction and older customers are more likely to intend to buy.
- **Price shows almost no linear relationship** with purchase intent in this dataset.
- **Purchase frequency** shows no meaningful linear relationship with intent.
- The dataset is **balanced across categories and brands**, so comparisons between them are not skewed by sample size.

> ⚠️ These are linear correlations on a single dataset; they indicate association, not causation.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook, JupyterLab, or Google Colab

### Installation

```bash
# Clone the repository
git clone https://github.com/Shiva2202/<your-repo-name>.git
cd <your-repo-name>

# (Optional) create a virtual environment
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter
```

### Run the notebook

```bash
jupyter notebook Consumer_Electronics_Sales_Data_Analysis_prediction.ipynb
```

> **Note:** The notebook loads data from `/content/consumer_electronics_sales_data.csv` (the Google Colab path). If running locally, change `file_path` in the data-loading cell to:
>
> ```python
> file_path = 'consumer_electronics_sales_data.csv'
> ```

You can also open the notebook directly in Google Colab and upload the CSV to the session.

---

## 🛣️ Roadmap

The notebook currently covers EDA. Planned next steps for the **prediction** component:

- [ ] Encode categorical features (`ProductCategory`, `ProductBrand`)
- [ ] Train/test split and feature scaling
- [ ] Baseline models: Logistic Regression, Decision Tree
- [ ] Advanced models: Random Forest, Gradient Boosting (XGBoost / LightGBM)
- [ ] Evaluate with accuracy, precision, recall, F1, and ROC-AUC
- [ ] Hyperparameter tuning and cross-validation
- [ ] Feature-importance analysis

---

## 🧰 Tech Stack

- **Language:** Python
- **Data handling:** pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Environment:** Jupyter Notebook / Google Colab

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome. Feel free to open an issue or submit a pull request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/new-analysis`)
3. Commit your changes (`git commit -m "Add new analysis"`)
4. Push to the branch (`git push origin feature/new-analysis`)
5. Open a pull request

---

## 👤 Author

**Borath Shiva Kumar**
GitHub: [@Shiva2202](https://github.com/Shiva2202)
