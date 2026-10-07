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
| p_1 | -1.006925 | 0.365341 | -1.006925 | 0.335666 | [0.189223, 0.705379] | 0.002702 | 0.008105 |
| p_2 | -0.933292 | 0.393257 | -0.933292 | 0.283565 | [0.22558, 0.685571] | 0.000997 | 0.002992 |
| p_4 | -0.253247 | 0.776276 | -0.253247 | 0.291093 | [0.438766, 1.373408] | 0.384308 | 1 |

*Baseline (reference) persona: **p_3**; its coefficient is absorbed by the intercept and is not shown.*

**How to say it in words:** 

*Persona X had an odds ratio of OR compared with the baseline persona; a value above 1 means it was more likely to get a reply and below 1 means less likely. The 95% CI was [low, high], so because it did/did not include 1 the result was/was not statistically significant (raw p = P, Bonferroni p = Q).*

## Raw Counts

### How to read these counts

Each row is one persona that actually attempted at least one thread (personas with zero attempts are placeholders and are omitted). Assigned is how many distinct scammers were assigned to the persona, Attempts is how many threads we started, Conversations (replied) is how many reached the reply minimum, and Response rate is conversations as a percent of attempts.

| Persona | Assigned | Attempts | Conversations (replied) | Response rate |
| --- | --- | --- | --- | --- |
| p_1 | 179 | 179 | 17 | 9.5 |
| p_2 | 335 | 335 | 34 | 10.15 |
| p_3 | 121 | 121 | 27 | 22.31 |
| p_4 | 182 | 181 | 33 | 18.23 |

## Engagement Depth (Mann-Whitney U)

### How to read the engagement-depth table

Each row compares two personas on one metric using the Mann-Whitney U test. The null hypothesis is that the two personas have the same distribution of that metric. U is the test statistic, nA and nB are the numbers of conversations in each group, p (raw) is the unadjusted p-value, and p (Bonferroni) multiplies the raw p by the number of pairs tested (capped at 1) to reduce false positives from many comparisons. A small p means the two groups are unlikely to be the same.

| Persona A | Persona B | Metric | nA | nB | U | p (raw) | p (Bonferroni) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| p_1 | p_2 | total_messages | 17 | 34 | 270.5 | 0.666907 | 1 |
| p_1 | p_3 | total_messages | 17 | 27 | 153 | 0.046361 | 0.278163 |
| p_1 | p_4 | total_messages | 17 | 33 | 203.5 | 0.088334 | 0.530003 |
| p_2 | p_3 | total_messages | 34 | 27 | 333 | 0.042287 | 0.253725 |
| p_2 | p_4 | total_messages | 34 | 33 | 444.5 | 0.105947 | 0.635682 |
| p_3 | p_4 | total_messages | 27 | 33 | 503.5 | 0.366487 | 1 |
| p_1 | p_2 | duration_days | 17 | 34 | 376 | 0.083919 | 0.503513 |
| p_1 | p_3 | duration_days | 17 | 27 | 250 | 0.629758 | 1 |
| p_1 | p_4 | duration_days | 17 | 33 | 305 | 0.623063 | 1 |
| p_2 | p_3 | duration_days | 34 | 27 | 347 | 0.105446 | 0.632677 |
| p_2 | p_4 | duration_days | 34 | 33 | 398 | 0.041555 | 0.249331 |
| p_3 | p_4 | duration_days | 27 | 33 | 448 | 0.976292 | 1 |

**How to say it in words:** 

*Comparing persona A with persona B on metric M, the Mann-Whitney U was U with nA and nB conversations respectively. The raw p-value was P and the Bonferroni-adjusted p-value was Q; since the adjusted p-value was/was not below 0.05, the difference was/was not statistically significant.*

## References

- statsmodels GLM: https://www.statsmodels.org/stable/glm.html
- Odds ratio: https://en.wikipedia.org/wiki/Odds_ratio
- Wald test: https://en.wikipedia.org/wiki/Wald_test
- Bonferroni correction: https://en.wikipedia.org/wiki/Bonferroni_correction
- scipy.stats.mannwhitneyu: https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.mannwhitneyu.html
- Statistical significance: https://en.wikipedia.org/wiki/Statistical_significance
