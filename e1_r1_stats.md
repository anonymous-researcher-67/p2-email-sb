# Statistical Report (minimum replies >= 1)

## Introduction

This report summarises how scammers engaged with each baiting persona. A "minimum replies >= 1" filter is applied: a conversation only counts when the scammer sent at least 1 genuine reply strictly AFTER our first outbound message in that thread. Inbound messages that arrived before our first outbound, and inbounds addressed to CRAWLER, do not count as replies. Every count below is taken from that qualifying set.

## Legend / Glossary

| Term | Plain meaning | How to read it |
| --- | --- | --- |
| Persona | A fake identity we use to bait scammers. | Each table row or chart bar is one persona unless it says Total. |
| Assigned scammers | How many distinct scammers the database assigned to the persona. | It can exceed Attempts when some assigned scammers never wrote back. |
| Attempt | A thread where at least one outbound message was sent to a scammer. | Counts every thread we started, whether or not the scammer replied. |
| Conversation | An attempt where the scammer sent at least the required replies. | The successful subset of the attempts. |
| Failed/Insufficient | Attempts that did not reach the reply minimum. | Attempts minus conversations. |
| Response rate | Share of attempts that became conversations, as a percent. | Conversations divided by attempts, multiplied by 100. |
| baseline persona | The reference persona the others are compared against. | It has no row in the logistic table; its effect sits inside the intercept. |
| intercept | The model's baseline log-odds for the baseline persona. | Rarely interpreted directly; shown only for completeness. |
| Coefficient | The modelled change in log-odds for a persona versus the baseline. | Positive means more likely, negative means less likely, than the baseline. |
| OR (odds ratio) | exp of the coefficient, an easier-to-read multiplier. | Above 1 means a higher reply chance than the baseline, below 1 means lower. |
| ln(OR) | The coefficient expressed as a logarithm of the odds ratio. | Carries the same information as the coefficient. |
| Standard Error | How uncertain the coefficient estimate is. | Smaller means a more precise estimate. |
| 95% Wald CI | A plausible range for the odds ratio. | If the range includes 1, the result is not statistically significant. |
| Raw p | Chance of seeing this result if there were truly no difference. | Below 0.05 is the conventional significance threshold. |
| Bonferroni p | Raw p multiplied by the number of comparisons, capped at 1. | A stricter p-value that guards against false positives from many tests. |
| Mann-Whitney U | A rank-based test comparing two groups without assuming a bell curve. | A small p-value suggests the two groups really differ. |
| nA/nB | Number of observations in group A and in group B. | Very small groups make the test unreliable. |
| pairwise comparison | A test of two personas against each other. | Testing many pairs raises the chance of a false positive. |
| null hypothesis | The assumption that the two groups are really the same. | We look for evidence strong enough to reject it. |
| p-value | Probability of the data if the null hypothesis were true. | Smaller values mean stronger evidence of a real difference. |
| multiple-comparison correction | Adjusting p-values when many tests are run at once. | We use Bonferroni, multiplying each raw p by the number of tests. |

## Response Rate Significance (logistic regression)

### How to read the logistic-regression table

The baseline persona is absorbed into the model intercept and therefore has no row of its own. Each other persona is compared with that baseline. An odds ratio (OR) above 1 means the persona had a higher chance of a reply than the baseline; below 1 means a lower chance; about 1 means little or no practical difference. The 95% Wald CI is the plausible range for the OR: if it includes 1, the difference is not statistically significant. Raw p is the uncorrected p-value, while Bonferroni p is raw p multiplied by the number of comparisons and capped at 1. The usual significance threshold is 0.05.

| Persona | Coefficient | OR | ln(OR) | Std Error | 95% Wald CI | Raw p | Bonferroni p |
| --- | --- | --- | --- | --- | --- | --- | --- |
| p_1 | -0.606817 | 0.545083 | -0.606817 | 0.240178 | [0.340423, 0.872783] | 0.011519 | 0.046078 |
| p_2 | -0.567951 | 0.566686 | -0.567951 | 0.245368 | [0.350333, 0.91665] | 0.02063 | 0.08252 |
| p_3 | -0.24632 | 0.781672 | -0.24632 | 0.248347 | [0.480427, 1.271807] | 0.321275 | 1 |
| p_5 | -0.575042 | 0.562681 | -0.575042 | 0.254311 | [0.341813, 0.926268] | 0.023749 | 0.094994 |

*Baseline (reference) persona: **p_4**; its coefficient is absorbed by the intercept and is not shown.*

**How to say it in words:** 

*Persona X had an odds ratio of OR compared with the baseline persona; a value above 1 means it was more likely to get a reply and below 1 means less likely. The 95% CI was [low, high], so because it did/did not include 1 the result was/was not statistically significant (raw p = P, Bonferroni p = Q).*

## Raw Counts

### How to read these counts

Each row is one persona that actually attempted at least one thread (personas with zero attempts are placeholders and are omitted). Assigned is how many distinct scammers were assigned to the persona, Attempts is how many threads we started, Conversations (replied) is how many reached the reply minimum, and Response rate is conversations as a percent of attempts.

| Persona | Assigned | Attempts | Conversations (replied) | Response rate |
| --- | --- | --- | --- | --- |
| p_1 | 180 | 179 | 44 | 24.58 |
| p_2 | 163 | 162 | 41 | 25.31 |
| p_3 | 135 | 135 | 43 | 31.85 |
| p_4 | 155 | 155 | 58 | 37.42 |
| p_5 | 143 | 143 | 36 | 25.17 |

## Engagement Depth (Mann-Whitney U)

### How to read the engagement-depth table

Each row compares two personas on one metric using the Mann-Whitney U test. The null hypothesis is that the two personas have the same distribution of that metric. U is the test statistic, nA and nB are the numbers of conversations in each group, p (raw) is the unadjusted p-value, and p (Bonferroni) multiplies the raw p by the number of pairs tested (capped at 1) to reduce false positives from many comparisons. A small p means the two groups are unlikely to be the same.

| Persona A | Persona B | Metric | nA | nB | U | p (raw) | p (Bonferroni) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| p_1 | p_2 | total_messages | 44 | 41 | 809 | 0.383624 | 1 |
| p_1 | p_3 | total_messages | 44 | 43 | 802 | 0.195824 | 1 |
| p_1 | p_4 | total_messages | 44 | 58 | 1357 | 0.547473 | 1 |
| p_1 | p_5 | total_messages | 44 | 36 | 777 | 0.878876 | 1 |
| p_2 | p_3 | total_messages | 41 | 43 | 835 | 0.667591 | 1 |
| p_2 | p_4 | total_messages | 41 | 58 | 1390 | 0.123384 | 1 |
| p_2 | p_5 | total_messages | 41 | 36 | 796.5 | 0.529132 | 1 |
| p_3 | p_4 | total_messages | 43 | 58 | 1538.5 | 0.032114 | 0.321142 |
| p_3 | p_5 | total_messages | 43 | 36 | 898 | 0.199913 | 1 |
| p_4 | p_5 | total_messages | 58 | 36 | 942 | 0.386319 | 1 |
| p_1 | p_2 | duration_days | 44 | 41 | 749 | 0.179856 | 1 |
| p_1 | p_3 | duration_days | 44 | 43 | 897 | 0.680525 | 1 |
| p_1 | p_4 | duration_days | 44 | 58 | 1438 | 0.275185 | 1 |
| p_1 | p_5 | duration_days | 44 | 36 | 796 | 0.972998 | 1 |
| p_2 | p_3 | duration_days | 41 | 43 | 1007 | 0.263322 | 1 |
| p_2 | p_4 | duration_days | 41 | 58 | 1528 | 0.01619 | 0.1619 |
| p_2 | p_5 | duration_days | 41 | 36 | 870 | 0.179422 | 1 |
| p_3 | p_4 | duration_days | 43 | 58 | 1482 | 0.107269 | 1 |
| p_3 | p_5 | duration_days | 43 | 36 | 813 | 0.7047 | 1 |
| p_4 | p_5 | duration_days | 58 | 36 | 908 | 0.291925 | 1 |

**How to say it in words:** 

*Comparing persona A with persona B on metric M, the Mann-Whitney U was U with nA and nB conversations respectively. The raw p-value was P and the Bonferroni-adjusted p-value was Q; since the adjusted p-value was/was not below 0.05, the difference was/was not statistically significant.*

## References

- statsmodels GLM: https://www.statsmodels.org/stable/glm.html
- Odds ratio: https://en.wikipedia.org/wiki/Odds_ratio
- Wald test: https://en.wikipedia.org/wiki/Wald_test
- Bonferroni correction: https://en.wikipedia.org/wiki/Bonferroni_correction
- scipy.stats.mannwhitneyu: https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.mannwhitneyu.html
- Statistical significance: https://en.wikipedia.org/wiki/Statistical_significance
