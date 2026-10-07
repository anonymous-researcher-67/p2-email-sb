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
| h_3x2 | -0.364596 | 0.694477 | -0.364596 | 0.237557 | [0.435958, 1.106294] | 0.12484 | 0.998716 |
| h_5x1 | -0.716022 | 0.488692 | -0.716022 | 0.237205 | [0.306989, 0.777945] | 0.00254 | 0.020317 |
| p_1 | -0.576909 | 0.561631 | -0.576909 | 0.23924 | [0.351404, 0.897628] | 0.01589 | 0.127121 |
| p_2 | -0.503655 | 0.604318 | -0.503655 | 0.243331 | [0.375092, 0.973627] | 0.038467 | 0.307739 |
| p_3 | -0.24632 | 0.781672 | -0.24632 | 0.248347 | [0.480427, 1.271807] | 0.321275 | 1 |
| p_5 | -0.502106 | 0.605255 | -0.502106 | 0.251774 | [0.369508, 0.991408] | 0.046122 | 0.368979 |
| p_6 | -0.560247 | 0.571068 | -0.560247 | 0.243906 | [0.354055, 0.921096] | 0.02162 | 0.172961 |
| p_7 | -0.69183 | 0.500659 | -0.69183 | 0.23494 | [0.315906, 0.793463] | 0.003233 | 0.02586 |

*Baseline (reference) persona: **p_4**; its coefficient is absorbed by the intercept and is not shown.*

**How to say it in words:** 

*Persona X had an odds ratio of OR compared with the baseline persona; a value above 1 means it was more likely to get a reply and below 1 means less likely. The 95% CI was [low, high], so because it did/did not include 1 the result was/was not statistically significant (raw p = P, Bonferroni p = Q).*

## Raw Counts

### How to read these counts

Each row is one persona that actually attempted at least one thread (personas with zero attempts are placeholders and are omitted). Assigned is how many distinct scammers were assigned to the persona, Attempts is how many threads we started, Conversations (replied) is how many reached the reply minimum, and Response rate is conversations as a percent of attempts.

| Persona | Assigned | Attempts | Conversations (replied) | Response rate |
| --- | --- | --- | --- | --- |
| h_3x2 | 168 | 167 | 49 | 29.34 |
| h_5x1 | 199 | 199 | 45 | 22.61 |
| p_1 | 180 | 179 | 45 | 25.14 |
| p_2 | 163 | 162 | 43 | 26.54 |
| p_3 | 135 | 135 | 43 | 31.85 |
| p_4 | 155 | 155 | 58 | 37.42 |
| p_5 | 143 | 143 | 38 | 26.57 |
| p_6 | 165 | 165 | 42 | 25.45 |
| p_7 | 204 | 204 | 47 | 23.04 |

## Engagement Depth (Mann-Whitney U)

### How to read the engagement-depth table

Each row compares two personas on one metric using the Mann-Whitney U test. The null hypothesis is that the two personas have the same distribution of that metric. U is the test statistic, nA and nB are the numbers of conversations in each group, p (raw) is the unadjusted p-value, and p (Bonferroni) multiplies the raw p by the number of pairs tested (capped at 1) to reduce false positives from many comparisons. A small p means the two groups are unlikely to be the same.

| Persona A | Persona B | Metric | nA | nB | U | p (raw) | p (Bonferroni) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| h_3x2 | h_5x1 | total_messages | 49 | 45 | 1095.5 | 0.957098 | 1 |
| h_3x2 | p_1 | total_messages | 49 | 45 | 1107.5 | 0.970503 | 1 |
| h_3x2 | p_2 | total_messages | 49 | 43 | 962.5 | 0.453793 | 1 |
| h_3x2 | p_3 | total_messages | 49 | 43 | 838 | 0.076192 | 1 |
| h_3x2 | p_4 | total_messages | 49 | 58 | 1438.5 | 0.907777 | 1 |
| h_3x2 | p_5 | total_messages | 49 | 38 | 935 | 0.974288 | 1 |
| h_3x2 | p_6 | total_messages | 49 | 42 | 948 | 0.491862 | 1 |
| h_3x2 | p_7 | total_messages | 49 | 47 | 1064 | 0.492339 | 1 |
| h_5x1 | p_1 | total_messages | 45 | 45 | 1024.5 | 0.918862 | 1 |
| h_5x1 | p_2 | total_messages | 45 | 43 | 895 | 0.52227 | 1 |
| h_5x1 | p_3 | total_messages | 45 | 43 | 795.5 | 0.128915 | 1 |
| h_5x1 | p_4 | total_messages | 45 | 58 | 1334 | 0.834872 | 1 |
| h_5x1 | p_5 | total_messages | 45 | 38 | 884 | 0.777365 | 1 |
| h_5x1 | p_6 | total_messages | 45 | 42 | 877.5 | 0.537879 | 1 |
| h_5x1 | p_7 | total_messages | 45 | 47 | 992.5 | 0.584028 | 1 |
| p_1 | p_2 | total_messages | 45 | 43 | 883 | 0.457864 | 1 |
| p_1 | p_3 | total_messages | 45 | 43 | 787 | 0.112914 | 1 |
| p_1 | p_4 | total_messages | 45 | 58 | 1319 | 0.921875 | 1 |
| p_1 | p_5 | total_messages | 45 | 38 | 877 | 0.832439 | 1 |
| p_1 | p_6 | total_messages | 45 | 42 | 871 | 0.502031 | 1 |
| p_1 | p_7 | total_messages | 45 | 47 | 985 | 0.543792 | 1 |
| p_2 | p_3 | total_messages | 43 | 43 | 836 | 0.431937 | 1 |
| p_2 | p_4 | total_messages | 43 | 58 | 1372.5 | 0.360603 | 1 |
| p_2 | p_5 | total_messages | 43 | 38 | 902.5 | 0.398607 | 1 |
| p_2 | p_6 | total_messages | 43 | 42 | 915.5 | 0.912013 | 1 |
| p_2 | p_7 | total_messages | 43 | 47 | 1031.5 | 0.861696 | 1 |
| p_3 | p_4 | total_messages | 43 | 58 | 1521 | 0.046236 | 1 |
| p_3 | p_5 | total_messages | 43 | 38 | 1009.5 | 0.057291 | 1 |
| p_3 | p_6 | total_messages | 43 | 42 | 1003 | 0.361115 | 1 |
| p_3 | p_7 | total_messages | 43 | 47 | 1132.5 | 0.303186 | 1 |
| p_4 | p_5 | total_messages | 58 | 38 | 1098.5 | 0.98058 | 1 |
| p_4 | p_6 | total_messages | 58 | 42 | 1104.5 | 0.394137 | 1 |
| p_4 | p_7 | total_messages | 58 | 47 | 1240 | 0.392304 | 1 |
| p_5 | p_6 | total_messages | 38 | 42 | 716.5 | 0.406809 | 1 |
| p_5 | p_7 | total_messages | 38 | 47 | 800 | 0.38213 | 1 |
| p_6 | p_7 | total_messages | 42 | 47 | 995 | 0.947592 | 1 |
| h_3x2 | h_5x1 | duration_days | 49 | 45 | 1178 | 0.570268 | 1 |
| h_3x2 | p_1 | duration_days | 49 | 45 | 1107 | 0.975848 | 1 |
| h_3x2 | p_2 | duration_days | 49 | 43 | 826 | 0.075666 | 1 |
| h_3x2 | p_3 | duration_days | 49 | 43 | 1022 | 0.808321 | 1 |
| h_3x2 | p_4 | duration_days | 49 | 58 | 1521.5 | 0.531794 | 1 |
| h_3x2 | p_5 | duration_days | 49 | 38 | 929 | 0.989758 | 1 |
| h_3x2 | p_6 | duration_days | 49 | 42 | 909 | 0.341425 | 1 |
| h_3x2 | p_7 | duration_days | 49 | 47 | 1189 | 0.786252 | 1 |
| h_5x1 | p_1 | duration_days | 45 | 45 | 951.5 | 0.625395 | 1 |
| h_5x1 | p_2 | duration_days | 45 | 43 | 708 | 0.030618 | 1 |
| h_5x1 | p_3 | duration_days | 45 | 43 | 885 | 0.493664 | 1 |
| h_5x1 | p_4 | duration_days | 45 | 58 | 1325 | 0.89684 | 1 |
| h_5x1 | p_5 | duration_days | 45 | 38 | 790 | 0.5555 | 1 |
| h_5x1 | p_6 | duration_days | 45 | 42 | 772 | 0.142857 | 1 |
| h_5x1 | p_7 | duration_days | 45 | 47 | 1037 | 0.875863 | 1 |
| p_1 | p_2 | duration_days | 45 | 43 | 763 | 0.08859 | 1 |
| p_1 | p_3 | duration_days | 45 | 43 | 926 | 0.732165 | 1 |
| p_1 | p_4 | duration_days | 45 | 58 | 1401 | 0.525444 | 1 |
| p_1 | p_5 | duration_days | 45 | 38 | 852 | 0.98177 | 1 |
| p_1 | p_6 | duration_days | 45 | 42 | 825 | 0.310083 | 1 |
| p_1 | p_7 | duration_days | 45 | 47 | 1078 | 0.875863 | 1 |
| p_2 | p_3 | duration_days | 43 | 43 | 1097 | 0.137395 | 1 |
| p_2 | p_4 | duration_days | 43 | 58 | 1575 | 0.024491 | 0.881689 |
| p_2 | p_5 | duration_days | 43 | 38 | 988 | 0.106625 | 1 |
| p_2 | p_6 | duration_days | 43 | 42 | 998 | 0.406175 | 1 |
| p_2 | p_7 | duration_days | 43 | 47 | 1255 | 0.048729 | 1 |
| p_3 | p_4 | duration_days | 43 | 58 | 1403 | 0.285519 | 1 |
| p_3 | p_5 | duration_days | 43 | 38 | 844 | 0.801979 | 1 |
| p_3 | p_6 | duration_days | 43 | 42 | 820 | 0.468351 | 1 |
| p_3 | p_7 | duration_days | 43 | 47 | 1086 | 0.54463 | 1 |
| p_4 | p_5 | duration_days | 58 | 38 | 1016 | 0.521804 | 1 |
| p_4 | p_6 | duration_days | 58 | 42 | 975 | 0.090347 | 1 |
| p_4 | p_7 | duration_days | 58 | 47 | 1295 | 0.66357 | 1 |
| p_5 | p_6 | duration_days | 38 | 42 | 706 | 0.378014 | 1 |
| p_5 | p_7 | duration_days | 38 | 47 | 927 | 0.76715 | 1 |
| p_6 | p_7 | duration_days | 42 | 47 | 1137 | 0.219194 | 1 |

**How to say it in words:** 

*Comparing persona A with persona B on metric M, the Mann-Whitney U was U with nA and nB conversations respectively. The raw p-value was P and the Bonferroni-adjusted p-value was Q; since the adjusted p-value was/was not below 0.05, the difference was/was not statistically significant.*

## References

- statsmodels GLM: https://www.statsmodels.org/stable/glm.html
- Odds ratio: https://en.wikipedia.org/wiki/Odds_ratio
- Wald test: https://en.wikipedia.org/wiki/Wald_test
- Bonferroni correction: https://en.wikipedia.org/wiki/Bonferroni_correction
- scipy.stats.mannwhitneyu: https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.mannwhitneyu.html
- Statistical significance: https://en.wikipedia.org/wiki/Statistical_significance
