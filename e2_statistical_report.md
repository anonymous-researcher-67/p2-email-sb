# Statistical Analysis Report: Experiment 2 (Culture & Romance)

This document provides a plain-text breakdown of the mathematical significance of our data.

## 1. Response Rate Significance (Logistic Regression)
We use Logistic Regression to see if a specific persona trait actually changes the probability of a scammer replying. A p-value below 0.05 means the effect is statistically significant (not just random luck).

### Regression Results (Baseline: Origin: Nigerian, Intent: Not-Seeking):
#### How to Read These Results:
- **Coefficient**: The specific variable or condition being tested against the baseline.
- **Estimate (OR)**: The Odds Ratio. An OR > 1 means the outcome is more likely than the baseline. An OR < 1 means it is less likely.
- **std. error**: Measures the precision of the estimate. Smaller values indicate higher precision.
- **p**: The p-value indicates statistical significance. A value < 0.05 proves the effect is real and not just random noise.

- **const**: OR = 0.106, std. error = 0.167, p = 0.000 (Significant). This is the baseline intercept.
- **Origin_European**: OR = 2.230, std. error = 0.207, p = 0.000 (Significant). This condition makes the target outcome 2.23 times more/less likely compared to the baseline.
- **Intent_Seeking**: OR = 1.108, std. error = 0.212, p = 0.627 (Not Significant). The difference measured here could just be random noise.

---

## 2. Engagement Depth (Mann-Whitney U Test)
We use the Mann-Whitney U test to compare continuous numbers (like 'total messages' or 'duration in days') between personas. We use this instead of a standard t-test because our data is usually skewed (a few very long conversations and many short ones).

### Comparing 'p_3' vs 'p_2'
- **Total Messages Exchanged**: p = 0.042 (Significant). There is a mathematical difference in message volume between p_3 and p_2.
- **Conversation Duration (Days)**: p = 0.093 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_3' vs 'p_4'
- **Total Messages Exchanged**: p = 0.366 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.982 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_3' vs 'p_1'
- **Total Messages Exchanged**: p = 0.046 (Significant). There is a mathematical difference in message volume between p_3 and p_1.
- **Conversation Duration (Days)**: p = 0.647 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_2' vs 'p_4'
- **Total Messages Exchanged**: p = 0.106 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.039 (Significant). There is a mathematical difference in retention duration between p_2 and p_4.

### Comparing 'p_2' vs 'p_1'
- **Total Messages Exchanged**: p = 0.667 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.087 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_4' vs 'p_1'
- **Total Messages Exchanged**: p = 0.088 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.630 (Not Significant). There is no real statistical difference in how long scammers talk to them.

