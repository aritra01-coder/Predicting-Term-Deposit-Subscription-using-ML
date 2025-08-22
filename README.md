 ![Results](https://github.com/aritra01-coder/Predicting-Term-Deposit-Subscription-using-ML/blob/46468705ab3f3bda53f1efe2d51f3329e0ac6647/td-to-managed-fund-transition.jpg)

# Predicting-Term-Deposit-Subscription-using-ML


---

## 1. Introduction
In the highly competitive banking sector, optimizing marketing efforts is paramount for profitability. Term deposits are a crucial source of funding for banks, and increasing subscriptions is a key objective. However, traditional mass marketing campaigns are often inefficient and costly, failing to precisely target individuals likely to subscribe. This leads to wasted resources and suboptimal conversion rates.  

This report outlines a **data-driven approach** using machine learning to identify potential term deposit subscribers more effectively, thereby enabling targeted marketing strategies.

---

## 2. Problem Statement
The core business problem is to improve the efficiency of the bank's term deposit marketing campaigns. This is hindered by the inability to accurately identify which clients are likely to subscribe to a term deposit, as indicated by the target variable **'y'**.  

Current approach → wasted resources on clients unlikely to subscribe.  
Desired outcome → develop a **reliable prediction method** for 'y' to enable targeted marketing efforts, reducing costs and increasing conversion success.

---

## 3. Dataset Description
The **Bank Marketing Dataset** contains data related to direct marketing campaigns (phone calls) conducted by a Portuguese banking institution.  

**Goal**: Predict whether a client will subscribe to a term deposit (binary classification: yes/no).

### Key Characteristics:
- **Instances**: 45,211 records
- **Attributes**: 17 input features + 1 output variable

### Important Features:
| Feature   | Description |
|-----------|-------------|
| age       | Age of the client |
| job       | Job type (admin., technician, blue-collar, etc.) |
| marital   | Marital status (married, single, etc.) |
| education | Education level |
| default   | Has credit in default? (yes/no) |
| balance   | Average yearly balance (in euros) |
| housing   | Has a housing loan? (yes/no) |
| loan      | Has a personal loan? (yes/no) |
| contact   | Communication type (cellular, telephone) |
| day       | Last contact day of the month |
| month     | Last contact month |
| duration  | Duration of last contact (seconds) |
| campaign  | Number of contacts during this campaign |
| pdays     | Days since last contact (-1 means never) |
| previous  | Number of contacts before this campaign |
| poutcome  | Outcome of previous campaign (success/failure/other) |

**Target Variable**:  
- **y** — Client subscribed to a term deposit? (yes/no)

---

## 4. Data Analysis Summary

### Descriptive Statistics:
- **Numerical Features** (e.g., age, duration, campaign) → variability in distributions.
- Outliers in `campaign` suggest over-contacted clients with no conversion.  
**Implication**: Over-contacting may harm customer trust and ROI.

### Value Counts (Categorical Features):
- Distribution of job, marital, and education analyzed.  
- Loan/default status provided risk insights.  
**Implication**: Enables targeted messaging for each group.

### Histograms:
- **Duration** → skewed distribution with long tail (few very long, successful calls).  
**Implication**: Long call duration may correlate with conversions.

### Countplots (Categorical Features vs Target):
- **Contact** → Cellular contacts yield higher conversions.  
- **Month** → Higher success in March, September, October, December.  
- **Previous Campaign Outcome** → Past success strongly predicts current success.  

**Actionable Insight**:  
Prioritize cellular outreach, focus campaigns in high-success months, and target clients with positive campaign history.

### Correlation Heatmap:
- Strong correlations among `emp.var.rate`, `euribor3m`, `nr.employed`.  
**Implication**: Indicates macroeconomic influence on behavior.

---

## 5. Methodology
1. **Data Loading & Inspection**  
   Loaded dataset, inspected structure, and ensured integrity.
   
2. **Preprocessing**  
   - One-hot encoding for categorical variables.  
   - StandardScaler for numerical features.  
   - Train-test split (80-20) for unbiased evaluation.  

3. **Model Selection**  
   - Decision Tree  
   - Random Forest  
   - kNN  
   - XGBoost  

4. **Training & Evaluation**  
   Trained models on processed data. Evaluated with accuracy, precision, recall, and F1-score.  
   **F1-score prioritized** due to imbalance in 'y'.

---

## 6. Model Evaluation & Selection
| Model          | Accuracy | Precision | Recall | F1-score |
|----------------|----------|-----------|--------|----------|
| Decision Tree  | 0.8871   | 0.5025    | 0.5316 | 0.5166   |
| Random Forest  | 0.9102   | 0.6516    | 0.4481 | 0.5311   |
| kNN            | 0.9007   | 0.5827    | 0.4406 | 0.5018   |
| **XGBoost**    | **0.9154** | **0.6466** | **0.5615** | **0.6010** |

✅ **Best Model: XGBoost** (highest F1-score, best balance between precision and recall).  

---

## 7. Prediction on New Data
To demonstrate model usage, predictions were made on **two unseen records**:  
- **Predictions**: `['no', 'no']`  

**Interpretation**: Both clients unlikely to subscribe → resources saved by avoiding targeting them.

---

## 8. Conclusion
This project successfully addressed the problem of predicting term deposit subscriptions.  
- XGBoost identified as the most effective model.  
- Model demonstrates strong potential for **improving targeted marketing**.

---

## 9. Business Implications
- 🎯 **Targeted Marketing**: Focus only on high-probability subscribers.  
- 📈 **Improved Conversion Rates**: Direct efforts towards promising leads.  
- 📊 **Strategic Campaign Planning**: Optimize contact method (cellular) and campaign timing (successful months).  
- 🧠 **Customer Understanding**: Segment customers for personalized campaigns.  
- 💰 **Cost Reduction**: Reduce waste on unlikely subscribers.

---



