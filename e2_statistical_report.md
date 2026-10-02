# Statistical Analysis Report: Experiment 2 (Culture & Romance)

This document provides a plain-text breakdown of the mathematical significance of our data.

## 1. Response Rate Significance (Logistic Regression)

We use logistic regression to test whether origin and relationship intent change the probability of a scammer replying. The baseline is Origin: Nigerian and Intent: Not-Seeking.

- CI method: 95% CI = exp( ln(OR) +/- 1.96 * std. error ), rounded to 2 decimals.
- The paper applies the Bonferroni correction only to Experiment 1. For reference, a Bonferroni adjustment over the two factor tests would give adjusted p = min(raw p x 2, 1.0).

| Coefficient | OR | ln(OR) | std. error | 95% CI (Wald) | p (raw) | Bonferroni p (reference) |
| --- | --- | --- | --- | --- | --- | --- |
| (intercept) | 0.106 | -2.244 | 0.167 | [0.08, 0.15] | <0.001 | n/a |
| Origin: Northern European | 2.230 | 0.802 | 0.207 | [1.49, 3.35] | <0.001 | <0.002 |
| Intent: Seeking Romance | 1.108 | 0.103 | 0.212 | [0.73, 1.68] | 0.627 | 1.000 |

Worked example for Origin:

- OR = 2.230, std. error = 0.207
- ln(2.230) = 0.802, and 1.96 * 0.207 = 0.406
- Lower: exp(0.802 - 0.406) = 1.49
- Upper: exp(0.802 + 0.406) = 3.35
- 95% CI = [1.49, 3.35]

Raw counts by persona:

| Persona | Condition | Initiated | Replied | Response rate |
| --- | --- | --- | --- | --- |
| p_1 | Nigerian / Seeking | 179 | 17 | 9.50% |
| p_2 | Nigerian / Not-Seeking | 335 | 34 | 10.15% |
| p_3 | European / Seeking | 121 | 27 | 22.31% |
| p_4 | European / Not-Seeking | 182 | 33 | 18.13% |
| Total | | 817 | 111 | 13.59% |

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

