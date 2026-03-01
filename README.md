# 🛍️ Customer Segmentation — Retail Shopping Trends

Unsupervised machine learning project that identifies distinct customer groups from a retail shopping dataset using **K-Means Clustering** and **RFM-based feature engineering**.

---

## 📁 Project Structure

```
customer-segmentation/
├── Customer_Segmentation.ipynb   # Main analysis notebook
├── shopping_trends.csv           # Source dataset (3,901 customers)
├── customer_segments_output.csv  # Final enriched output with segment labels
├── elbow_curve.png               # Optimal k selection chart
├── pca_clusters.png              # 2D PCA cluster visualization
├── cluster_heatmap.png           # Feature heatmap per cluster
├── radar_profile.png             # Radar chart of cluster profiles
├── spend_frequency.png           # Spend & frequency boxplots
├── segment_pie.png               # Segment distribution pie chart
└── README.md
```

---

## 📊 Dataset

**File:** `shopping_trends.csv` — 3,901 rows × 19 columns

| Column | Description |
|--------|-------------|
| Customer ID | Unique customer identifier |
| Age, Gender, Location | Demographic info |
| Purchase Amount (USD) | Transaction value |
| Category, Item Purchased | Product details |
| Previous Purchases | Number of prior transactions |
| Frequency of Purchases | Purchase cadence (Weekly, Monthly, etc.) |
| Review Rating | Customer rating (1–5) |
| Subscription Status | Active subscriber (Yes/No) |
| Discount Applied / Promo Code Used | Discount behavior |

---

## 🔬 Methodology

### Feature Engineering (RFM-Inspired)
| Feature | Description |
|---------|-------------|
| `Monetary` | Purchase amount (USD) |
| `Frequency` | Previous purchases count |
| `Recency_Score` | Mapped from purchase cadence (Weekly=7 … Annually=1) |
| `Loyalty_Flag` | Subscriber = 1, Non-subscriber = 0 |
| `Discount_Seeker` | Sum of discount + promo code usage |
| `High_Rater` | Rating ≥ 4.0 = 1 |
| `Age_Group` | Binned age (1=18-25, 2=26-35, 3=36-50, 4=51-70) |

### Clustering Pipeline
1. **StandardScaler** — normalize all features
2. **Elbow Method + Silhouette Score** — determine optimal `k`
3. **K-Means** — assign cluster labels
4. **PCA** — reduce to 2D for visualization

---

## 🧩 Customer Segments

| Segment | Profile | Strategy |
|---------|---------|----------|
| 💎 Champions | High spend, high frequency, loyal | VIP rewards, early access |
| 🛒 Frequent Shoppers | Buy often, moderate spend | Upsell bundles, volume discounts |
| 🏷️ Budget Buyers | Only buy with discounts/promos | Smart time-limited offers |
| 🌱 New/Occasional | Low frequency, few purchases | Onboarding journeys, welcome offers |
| 💤 At-Risk | Past regulars who slowed down | Win-back campaigns |

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Run the Notebook
```bash
jupyter notebook Customer_Segmentation.ipynb
```
Then select **Kernel → Restart & Run All**.

---

## 📈 Output

The notebook generates:
- **`customer_segments_output.csv`** — original data enriched with `Cluster` and `Segment` columns
- **6 PNG charts** saved to the working directory

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-yellowgreen?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas)

---

## 📄 License

MIT License — free to use, modify, and distribute.
