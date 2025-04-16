# 🧪 A/B Testing Statistical Analysis (with Python & Stats Theory)

This project is a complete walkthrough of the **A/B testing process** using real-world theory, statistical validation, and data analysis techniques. It aims to simulate a real experimentation pipeline used by product teams to evaluate whether a new feature (e.g., button design, user interface, CTA wording) improves user behavior based on statistical evidence.

This project is based on the [FreeCodeCamp A/B Testing tutorial](https://youtu.be/FTpmwX94_Yo?si=j64-jlPtn7MiqfzQ) and extended with concepts and data from this GitHub repository:  
🔗 https://github.com/TatevKaren/CaseStudies/tree/main/AB%20Testing

---

## 🎯 Project Purpose

To demonstrate how companies can make **data-driven decisions** using proper statistical methods to compare two versions (control vs experimental) of a product element. The process includes:

- Formulating hypotheses
- Designing an A/B test (including power analysis)
- Running the experiment
- Evaluating statistical **and** practical significance

---

## 🧰 Tools & Technologies Used

| Tool     | Purpose                                |
|----------|----------------------------------------|
| Python (Pandas, Matplotlib, SciPy) | Data wrangling, statistical tests, and plotting |
| Jupyter Notebook | Interactive analysis & reporting |
| GitHub   | Version control and documentation      |

---

## 🧪 A/B Testing Framework

### 1. Hypothesis Definition

- **Business Hypothesis:**  
  > Changing the CTA from “Secure Free Trial” (A) to “Enroll Now” (B) will increase the conversion rate.

- **Statistical Hypotheses:**

  ```text
  H₀ (Null): P_control = P_experiment  
  H₁ (Alt):  P_control ≠ P_experiment
  ```

- **Primary Metric:** Conversion Rate  
  \( \text{Conversion Rate} = \frac{\text{Number of Conversions}}{\text{Total Visitors}} \times 100 \)

- Validated with the **Metric Validity Question**:  
  > If this metric increases and all else remains constant, does it address the problem?

---

### 2. A/B Test Design

- **Power Analysis**
- **Minimum Sample Size**
- **Expected Effect Size**
- **Test Duration Estimation**

Design goal: Determine how many users we need to observe significant effects and ensure statistical reliability.

---

### 3. Running the Experiment

- Load and explore the dataset
- Group results by experiment group and clicks
- Visualize click distribution

```python
# Sample code snippet
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv('ab_test_data.csv')
df.groupby('group')['converted'].mean().plot(kind='bar')
plt.title('Conversion Rate by Group')
plt.show()
```

---

## 📈 Statistical Significance Testing

### ✅ Steps Taken:

1. **Pooled Estimate** of conversion rate  
2. **Pooled Variance** and **Standard Error**  
3. **Z-test** for proportion differences

```python
from scipy.stats import norm

# Compute Z statistic
z_stat = (p_exp - p_con) / std_error
p_value = 2 * (1 - norm.cdf(abs(z_stat)))
```

4. **Critical Z-value for α = 0.05**  
   - If |Z| > 1.96 → Reject H₀
5. **Confidence Interval** construction

---

### 📉 Interpretation of Results

- **Test Statistic:** Extreme (e.g., Z = -59.44)
- **P-value:** Near 0 → **strong evidence against the null hypothesis**
- **Conclusion:** Reject the null. There's a statistically significant difference.

---

### 📊 Visualization

The Z-distribution plot includes:

- **Standard Normal Bell Curve**
- **Rejection Regions** (blue)
- **Critical Z-lines** (green)
- **Test Statistic Line** (red)

Interpretation:
> The test statistic lies far beyond the rejection threshold → result is **statistically significant**.

---

## 📊 Practical Significance

Statistical significance ≠ real-world usefulness. After rejecting H₀, we also evaluate:

- Is the effect size large enough to matter?
- Does the change justify design/coding cost?
- How does it align with business strategy?

---

## 📚 Skills Demonstrated

- A/B Testing Framework Design
- Hypothesis Formulation
- Metric Validity Evaluation
- Power Analysis & Sample Sizing
- Z-test and Confidence Intervals
- Python Statistical Coding
- Visual Interpretation of Results

---

## 🧑‍💼 Author

**Yeo Chee En Luke**  
Statistician & Computer Scientist  
📧 [Optional: insert email or LinkedIn]

---

## 🎓 Acknowledgements

Project inspired by:  
🎥 [FreeCodeCamp YouTube Tutorial](https://youtu.be/FTpmwX94_Yo?si=j64-jlPtn7MiqfzQ)  
📦 [TatevKaren Case Study GitHub](https://github.com/TatevKaren/CaseStudies/tree/main/AB%20Testing)

This was completed for educational purposes to solidify knowledge in statistics and experimentation.

---

 ![image](https://github.com/user-attachments/assets/30f6cf14-bba5-468e-aa37-ada395810872)
