# Statistical Analysis Report: Experiment 1 (Hybridization)

This document provides a plain-text breakdown of the mathematical significance of our data.

## 1. Response Rate Significance (Logistic Regression)
We use Logistic Regression to see if a specific persona trait actually changes the probability of a scammer replying. A p-value below 0.05 means the effect is statistically significant (not just random luck).

### Regression Results (Baseline: p_4):
#### How to Read These Results:
- **Coefficient**: The specific variable or condition being tested against the baseline.
- **Estimate (OR)**: The Odds Ratio. An OR > 1 means the outcome is more likely than the baseline. An OR < 1 means it is less likely.
- **std. error**: Measures the precision of the estimate. Smaller values indicate higher precision.
- **p**: The p-value indicates statistical significance. A value < 0.05 proves the effect is real and not just random noise.

- **const**: OR = 0.598, std. error = 0.166, p = 0.002 (Significant). This is the baseline intercept.
- **h_3x2**: OR = 0.694, std. error = 0.238, p = 0.125 (Not Significant). The difference measured here could just be random noise.
- **h_5x1**: OR = 0.489, std. error = 0.237, p = 0.003 (Significant). This condition makes the target outcome 0.49 times more/less likely compared to the baseline.
- **p_1**: OR = 0.562, std. error = 0.239, p = 0.016 (Significant). This condition makes the target outcome 0.56 times more/less likely compared to the baseline.
- **p_2**: OR = 0.604, std. error = 0.243, p = 0.038 (Significant). This condition makes the target outcome 0.60 times more/less likely compared to the baseline.
- **p_3**: OR = 0.782, std. error = 0.248, p = 0.321 (Not Significant). The difference measured here could just be random noise.
- **p_5**: OR = 0.605, std. error = 0.252, p = 0.046 (Significant). This condition makes the target outcome 0.61 times more/less likely compared to the baseline.
- **p_6**: OR = 0.571, std. error = 0.244, p = 0.022 (Significant). This condition makes the target outcome 0.57 times more/less likely compared to the baseline.
- **p_7**: OR = 0.501, std. error = 0.235, p = 0.003 (Significant). This condition makes the target outcome 0.50 times more/less likely compared to the baseline.

---

## 2. Engagement Depth (Mann-Whitney U Test)
We use the Mann-Whitney U test to compare continuous numbers (like 'total messages' or 'duration in days') between personas. We use this instead of a standard t-test because our data is usually skewed (a few very long conversations and many short ones).

### Comparing 'h_3x2' vs 'h_5x1'
- **Total Messages Exchanged**: p = 0.957 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.583 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_3x2' vs 'p_6'
- **Total Messages Exchanged**: p = 0.492 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.339 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_3x2' vs 'p_5'
- **Total Messages Exchanged**: p = 0.974 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 1.000 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_3x2' vs 'p_3'
- **Total Messages Exchanged**: p = 0.076 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.820 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_3x2' vs 'p_4'
- **Total Messages Exchanged**: p = 0.908 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.561 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_3x2' vs 'p_7'
- **Total Messages Exchanged**: p = 0.492 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.832 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_3x2' vs 'p_1'
- **Total Messages Exchanged**: p = 0.971 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.958 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_3x2' vs 'p_2'
- **Total Messages Exchanged**: p = 0.454 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.076 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_5x1' vs 'p_6'
- **Total Messages Exchanged**: p = 0.538 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.144 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_5x1' vs 'p_5'
- **Total Messages Exchanged**: p = 0.777 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.574 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_5x1' vs 'p_3'
- **Total Messages Exchanged**: p = 0.129 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.478 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_5x1' vs 'p_4'
- **Total Messages Exchanged**: p = 0.835 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.905 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_5x1' vs 'p_7'
- **Total Messages Exchanged**: p = 0.584 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.873 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_5x1' vs 'p_1'
- **Total Messages Exchanged**: p = 0.919 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.643 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'h_5x1' vs 'p_2'
- **Total Messages Exchanged**: p = 0.522 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.032 (Significant). There is a mathematical difference in retention duration between h_5x1 and p_2.

### Comparing 'p_6' vs 'p_5'
- **Total Messages Exchanged**: p = 0.407 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.370 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_6' vs 'p_3'
- **Total Messages Exchanged**: p = 0.361 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.458 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_6' vs 'p_4'
- **Total Messages Exchanged**: p = 0.394 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.088 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_6' vs 'p_7'
- **Total Messages Exchanged**: p = 0.948 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.221 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_6' vs 'p_1'
- **Total Messages Exchanged**: p = 0.502 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.308 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_6' vs 'p_2'
- **Total Messages Exchanged**: p = 0.912 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.404 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_5' vs 'p_3'
- **Total Messages Exchanged**: p = 0.057 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.806 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_5' vs 'p_4'
- **Total Messages Exchanged**: p = 0.981 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.549 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_5' vs 'p_7'
- **Total Messages Exchanged**: p = 0.382 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.777 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_5' vs 'p_1'
- **Total Messages Exchanged**: p = 0.832 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.993 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_5' vs 'p_2'
- **Total Messages Exchanged**: p = 0.399 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.109 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_3' vs 'p_4'
- **Total Messages Exchanged**: p = 0.046 (Significant). There is a mathematical difference in message volume between p_3 and p_4.
- **Conversation Duration (Days)**: p = 0.285 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_3' vs 'p_7'
- **Total Messages Exchanged**: p = 0.303 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.545 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_3' vs 'p_1'
- **Total Messages Exchanged**: p = 0.113 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.716 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_3' vs 'p_2'
- **Total Messages Exchanged**: p = 0.432 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.137 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_4' vs 'p_7'
- **Total Messages Exchanged**: p = 0.392 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.627 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_4' vs 'p_1'
- **Total Messages Exchanged**: p = 0.922 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.538 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_4' vs 'p_2'
- **Total Messages Exchanged**: p = 0.361 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.023 (Significant). There is a mathematical difference in retention duration between p_4 and p_2.

### Comparing 'p_7' vs 'p_1'
- **Total Messages Exchanged**: p = 0.544 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.910 (Not Significant). There is no real statistical difference in how long scammers talk to them.

### Comparing 'p_7' vs 'p_2'
- **Total Messages Exchanged**: p = 0.862 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.050 (Significant). There is a mathematical difference in retention duration between p_7 and p_2.

### Comparing 'p_1' vs 'p_2'
- **Total Messages Exchanged**: p = 0.458 (Not Significant). There is no real statistical difference in message volume between the two.
- **Conversation Duration (Days)**: p = 0.090 (Not Significant). There is no real statistical difference in how long scammers talk to them.

