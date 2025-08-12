# 💳 AtliQo Bank Credit Card Launch Campaign

## 📌 Project Overview
This project analyzes AtliQo Bank’s customer base to identify the best target segment for a **trial credit card launch** and evaluates the campaign's success using **statistical hypothesis testing**.

The project is divided into **two phases**:
1. **Phase 1:** 🎯 **Market Segmentation & Target Audience Identification**
2. **Phase 2:** 📊 **Campaign Impact Validation (Z-test)**

---

## 📂 Dataset
The dataset contains:
- **Demographics:** Age group, annual income
- **Financial Info:** Credit limit, credit score
- **Transaction Data:** Payment type usage, product categories
- **Experimental Groups:** Control group & Test group

---

## 🛠 Tools & Libraries
- **Python 3.x**
- `pandas` — Data manipulation  
- `matplotlib`, `seaborn` — Data visualization  
- `statsmodels` — Hypothesis testing (`ztest`)

---

## 📊 Phase 1: Market Analysis & Target Identification

### Key Visual Insights:
![Age group and financial metrics analysis](analysis.png)

### Findings:
- **Age group 18–25** = ~26% of the customer base.
- **Low annual income (~₹37K/year)** and **low credit score (~484)** — due to short credit history.
- **Low credit card usage** → untapped market potential.
- Top product categories:  
  1. Electronics  
  2. Fashion & Apparel  
  3. Beauty & Personal Care  

✅ **Decision:** Target the **18–25** age group for the pilot launch.

---

## 📈 Phase 2: Hypothesis Testing

**Goal:** Check if the campaign increased the average transaction amount in the test group.

### Hypothesis:
- **H₀:** μ_test ≤ μ_control  
- **H₁:** μ_test > μ_control  

### Z-test:
```python
from statsmodels.stats import weightstats as sm
z_stat, p_value = sm.ztest(
    df['test_group_avg_tran'],
    df['control_group_avg_tran'],
    alternative='larger'
)
