
# 🧪 Two-Way ANOVA: Impact of Exercise and Cholesterol on Systolic Blood Pressure

This project explores the influence of **exercise activity** and **cholesterol levels** on **systolic blood pressure (ap_hi)** using Two-Way ANOVA. Conducted as a final project for the course *Statistic Theory and Application (5301_001)* at the University of Texas at Arlington, the analysis was performed using R.

---

## 📌 Objective

To determine if physical activity (exercise) and cholesterol levels significantly affect systolic blood pressure, and whether their interaction plays a role in cardiovascular health.

---

## 📂 Dataset Overview

- **Source:** [Kaggle - Cardiovascular Dataset](https://www.kaggle.com/)
- **Original Size:** 70,000 rows × 13 columns
- **Selected Columns:**
  - `ap_hi`: Systolic blood pressure (continuous variable)
  - `cholesterol`: Cholesterol level (categorical; 1, 2, 3)
  - `active`: Physical activity status (binary; 0, 1)

---

## ⚙️ Data Preprocessing

- Removed irrelevant columns (`id`, `age`, `gender`, etc.)
- Converted `cholesterol` to a factor variable
- Applied Z-score normalization
- Selected chunks (~5000 records) for normality testing
- Used **Shapiro-Wilk** and **Levene’s Test** to validate assumptions

---

## 📈 Statistical Methods & Analysis

### ✅ Assumption Testing

- **Shapiro-Wilk Normality Test**: Performed on data chunks; most showed non-normality.
- **Levene’s Test**: Resulted in p ≈ 0.059 → assumed homogeneity of variance.

### 🔍 Two-Way ANOVA Results

| Factor              | p-value | Significance |
|---------------------|---------|--------------|
| Exercise (Active)   | 0.993   | ❌ Not significant |
| Cholesterol Level   | 4.29e-10 | ✅ Significant |
| Interaction         | 0.200   | ❌ Not significant |

---

## 🧪 Post Hoc Test (Tukey HSD)

Significant differences in systolic pressure were observed between:
- Cholesterol Level 2 vs 1: **p = 0.0000054**
- Cholesterol Level 3 vs 1: **p = 0.0000008**

---

## 📊 Visualizations

- **Scatter Plot**: Active vs Systolic BP by Cholesterol
- **Boxplot**: Systolic BP by Cholesterol
- **QQ Plots**: Normality check
- **ANOVA Table** and **Tukey Post Hoc Summary**

---

## 📌 Key Insights

1. **Cholesterol levels significantly impact systolic blood pressure.**
2. **Exercise alone** does not have a significant effect.
3. No interaction effect was observed between cholesterol and exercise.
4. Post hoc analysis highlighted cholesterol levels 2 and 3 as contributing to higher systolic BP.

---

## 📦 File Structure

```
├── cardio_train.csv
├── 5301-final-project Team 15.pdf
├── README.md
└── R analysis scripts
```

---

## 🧠 Conclusion

This project highlights that while physical activity may not independently reduce systolic pressure significantly, **cholesterol management** plays a critical role. The findings aid in understanding risk factors for cardiovascular conditions and support the design of effective health interventions.

---

## 🧰 Tools & Packages

- **Language:** R
- **Libraries:** `car`, `ggplot2`, `dplyr`, `stats`, `TukeyHSD`, `aov`, `scale`, `shapiro.test`

---

## ⚠️ Disclaimer

This study is for academic and research purposes only. It should not be used for real-world medical decision-making without further clinical validation.
