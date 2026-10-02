# Statistical Analysis Report: Experiment 1 (Hybridization)

This document provides a plain-text breakdown of the mathematical significance of our data.

## 1. Response Rate Significance (Logistic Regression)

We use logistic regression to test whether a persona changes the probability of a scammer replying. The baseline is p_4, the persona with the highest raw response rate.

For each coefficient we report the odds ratio (OR), the log-odds, the standard error of the log-odds, the Wald 95% confidence interval, the raw p-value, and the Bonferroni-adjusted p-value.

- CI method: 95% CI = exp( ln(OR) +/- 1.96 * std. error ), rounded to 2 decimals.
- Correction method: adjusted p = min(raw p x 8, 1.0), because eight personas are compared with the baseline.
- The intercept is not a persona test, so it is not corrected.

| Coefficient | OR | ln(OR) | std. error | 95% CI (Wald) | p (raw) | Bonferroni p |
| --- | --- | --- | --- | --- | --- | --- |
| (intercept) | 0.598 | -0.514 | 0.166 | [0.43, 0.83] | 0.002 | n/a |
| p_1 | 0.562 | -0.576 | 0.239 | [0.35, 0.90] | 0.016 | 0.128 |
| p_2 | 0.604 | -0.504 | 0.243 | [0.38, 0.97] | 0.038 | 0.304 |
| p_3 | 0.782 | -0.246 | 0.248 | [0.48, 1.27] | 0.321 | 1.000 |
| p_5 | 0.605 | -0.503 | 0.252 | [0.37, 0.99] | 0.046 | 0.368 |
| p_6 | 0.571 | -0.560 | 0.244 | [0.35, 0.92] | 0.022 | 0.176 |
| p_7 | 0.501 | -0.691 | 0.235 | [0.32, 0.79] | 0.003 | 0.024 |
| h_3x2 | 0.694 | -0.365 | 0.238 | [0.44, 1.11] | 0.125 | 1.000 |
| h_5x1 | 0.489 | -0.715 | 0.237 | [0.31, 0.78] | 0.003 | 0.024 |

After the Bonferroni correction, only p_7 and h_5x1 remain below 0.05 (adjusted p = 0.024 for both).

Worked example for p_1:

- OR = 0.562, std. error = 0.239
- ln(0.562) = -0.576, and 1.96 * 0.239 = 0.468
- Lower: exp(-0.576 - 0.468) = 0.35
- Upper: exp(-0.576 + 0.468) = 0.90
- 95% CI = [0.35, 0.90]

Raw counts by persona:

| Persona | Initiated | Replied | Response rate |
| --- | --- | --- | --- |
| p_1 | 179 | 45 | 25.14% |
| p_2 | 162 | 43 | 26.54% |
| p_3 | 135 | 43 | 31.85% |
| p_4 | 155 | 58 | 37.42% |
| p_5 | 143 | 38 | 26.57% |
| p_6 | 165 | 42 | 25.45% |
| p_7 | 204 | 47 | 23.04% |
| h_3x2 | 167 | 49 | 29.34% |
| h_5x1 | 199 | 45 | 22.61% |
| Total | 1509 | 410 | 27.17% |

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

