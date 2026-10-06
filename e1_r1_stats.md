# Statistical Report (minimum replies >= 1)

## Response Rate Significance (logistic regression)

| Persona | Coefficient | OR | ln(OR) | Std Error | 95% Wald CI | Raw p | Bonferroni p |
| --- | --- | --- | --- | --- | --- | --- | --- |
| p_1 | -0.606817 | 0.545083 | -0.606817 | 0.240178 | [0.340423, 0.872783] | 0.011519 | 0.046078 |
| p_2 | -0.567951 | 0.566686 | -0.567951 | 0.245368 | [0.350333, 0.91665] | 0.02063 | 0.08252 |
| p_3 | -0.24632 | 0.781672 | -0.24632 | 0.248347 | [0.480427, 1.271807] | 0.321275 | 1 |
| p_5 | -0.575042 | 0.562681 | -0.575042 | 0.254311 | [0.341813, 0.926268] | 0.023749 | 0.094994 |

*Baseline (reference) persona: **p_4**; its coefficient is absorbed by the intercept and is not shown.*

## Raw Counts

| Persona | Initiated (attempts) | Replied (conversations N) | Response rate |
| --- | --- | --- | --- |
| p_1 | 179 | 44 | 24.58 |
| p_2 | 162 | 41 | 25.31 |
| p_3 | 135 | 43 | 31.85 |
| p_4 | 155 | 58 | 37.42 |
| p_5 | 143 | 36 | 25.17 |

## Engagement Depth (Mann-Whitney U)

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
