# 💳 Credit Card Customer Segmentation and behavior analysis

**Goal:**  
Segment credit card customers based on their **spending patterns** and **repayment behavior** to help businesses:
- Design targeted offers 🎯  
- Improve customer retention 💡  
- Detect risky customers 🔍  

---

## 📌 Problem Statement
Credit card companies deal with a **diverse customer base** — some spend heavily and repay on time, while others default or keep high balances.  
A **one-size-fits-all approach** to marketing and risk management often fails.  
By **clustering customers into segments**, companies can tailor:
- Marketing campaigns
- Credit limit policies
- Retention strategies

---

## 📂 Dataset
- **Source:** [Kaggle - Credit Card Dataset](https://www.kaggle.com/datasets/arjunbhasin2013/ccdata)
- **Shape:** 8950 rows × 18 columns
- **Features:**
  - BALANCE, PURCHASES, CASH_ADVANCE
  - CREDIT_LIMIT, PAYMENTS, MINIMUM_PAYMENTS
  - Frequency features like PURCHASES_FREQUENCY, ONEOFF_PURCHASES_FREQUENCY

---

## 🛠 Project Workflow
### **1. Data Understanding & Cleaning**
- Checked missing values  
- Filled missing entries using a distribution-based imputation strategy  
- Removed obvious outliers where necessary

### **2. Exploratory Data Analysis (EDA)**
- Distribution plots for spending & repayment patterns  
- Correlation heatmap for feature relationships  
- Insights on customer behavior patterns

### **3. Feature Scaling**
- Standardized numerical features for fair clustering  
- Used **StandardScaler** from scikit-learn

### **4. Dimensionality Reduction**
- Applied **PCA** to reduce noise & improve clustering
- Retained ~85% variance with top components

### **5. Clustering (K-Means)**
- Elbow Method to determine optimal k  
- Silhouette Score for validation  
- Final model with **k=4** clusters

### **6. Cluster Profiling**
| Cluster | Key Traits |
|---------|------------|
| **0** | High balance, high purchases, high credit limit |
| **1** | High balance, mid purchases, high credit limit |
| **2** | Low balance, low purchases, varied credit limit |
| **3** | Moderate balance, high cash advances |

---

## 📊 Key Insights
- Customers with **one-off purchases** have a stronger correlation with total purchases than installment purchases.
- Some clusters have **very high credit limits** but low usage — potential targets for marketing.
- Negative correlation between **balance** and **full payment ratio** indicates higher balances may lead to partial repayments.

---

## 💡 Business Recommendations
1. **High spenders** (Cluster 0) → Offer **loyalty rewards** to maintain retention.  
2. **Mid spenders with high limits** (Cluster 1) → Cross-sell premium services.  
3. **Low activity customers** (Cluster 2) → Offer promotional discounts to boost usage.  
4. **High cash advance customers** (Cluster 3) → Monitor closely for default risk.  

---

## 📸 Visualizations
| PCA Clusters | Feature Distributions |
|--------------|-----------------------|
| ![Clusters](https://github.com/Soumodwip-Mondal/Credit-Card-Customer-Segmentaion/blob/main/chart_image/final_clusters.png)) | ![Distributions](https://github.com/Soumodwip-Mondal/Credit-Card-Customer-Segmentaion/blob/main/chart_image/distributions.png) |

---

## 🖥 Technologies Used
- **Python**: pandas, numpy, matplotlib, seaborn
- **Machine Learning**: scikit-learn (KMeans, PCA, silhouette score)
- **Data Visualization**: matplotlib, seaborn

---

## 🚀 How to Run
```bash
# Clone the repository
git clone https://github.com/Soumodwip-Mondal/Credit-Card-Customer-Segmentaion
cd credit_card_customer_segmentation

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook credit_card_customer_clustering.ipynb
