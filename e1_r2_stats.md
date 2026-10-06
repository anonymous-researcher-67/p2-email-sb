# Statistical Report (minimum replies >= 1)

## Response Rate Significance (logistic regression)

| Persona | Coefficient | OR | ln(OR) | Std Error | 95% Wald CI | Raw p | Bonferroni p |
| --- | --- | --- | --- | --- | --- | --- | --- |
| h_5x1 | -0.351426 | 0.703684 | -0.351426 | 0.239997 | [0.439631, 1.126334] | 0.143114 | 0.572455 |
| p_4 | -26.017068 | 0 | -26.017068 | 399776.0678 | [0, inf] | 0.999948 | 1 |
| p_6 | -0.19565 | 0.8223 | -0.19565 | 0.246622 | [0.507109, 1.333395] | 0.427591 | 1 |
| p_7 | -0.327234 | 0.720915 | -0.327234 | 0.237758 | [0.452377, 1.148861] | 0.168719 | 0.674874 |

*Baseline (reference) persona: **h_3x2**; its coefficient is absorbed by the intercept and is not shown.*

## Raw Counts

| Persona | Initiated (attempts) | Replied (conversations N) | Response rate |
| --- | --- | --- | --- |
| h_3x2 | 167 | 49 | 29.34 |
| h_5x1 | 199 | 45 | 22.61 |
| p_1 | 0 | 0 | 0 |
| p_2 | 0 | 0 | 0 |
| p_3 | 0 | 0 | 0 |
| p_4 | 3 | 0 | 0 |
| p_5 | 0 | 0 | 0 |
| p_6 | 165 | 42 | 25.45 |
| p_7 | 204 | 47 | 23.04 |

## Engagement Depth (Mann-Whitney U)

| Persona A | Persona B | Metric | nA | nB | U | p (raw) | p (Bonferroni) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| h_3x2 | h_5x1 | total_messages | 49 | 45 | 1095.5 | 0.957098 | 1 |
| h_3x2 | p_6 | total_messages | 49 | 42 | 948 | 0.491862 | 1 |
| h_3x2 | p_7 | total_messages | 49 | 47 | 1064 | 0.492339 | 1 |
| h_5x1 | p_6 | total_messages | 45 | 42 | 877.5 | 0.537879 | 1 |
| h_5x1 | p_7 | total_messages | 45 | 47 | 992.5 | 0.584028 | 1 |
| p_6 | p_7 | total_messages | 42 | 47 | 995 | 0.947592 | 1 |
| h_3x2 | h_5x1 | duration_days | 49 | 45 | 1178 | 0.570268 | 1 |
| h_3x2 | p_6 | duration_days | 49 | 42 | 909 | 0.341425 | 1 |
| h_3x2 | p_7 | duration_days | 49 | 47 | 1189 | 0.786252 | 1 |
| h_5x1 | p_6 | duration_days | 45 | 42 | 772 | 0.142857 | 0.85714 |
| h_5x1 | p_7 | duration_days | 45 | 47 | 1037 | 0.875863 | 1 |
| p_6 | p_7 | duration_days | 42 | 47 | 1137 | 0.219194 | 1 |
