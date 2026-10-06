# Statistical Report (minimum replies >= 1)

## Response Rate Significance (logistic regression)

| Persona | Coefficient | OR | ln(OR) | Std Error | 95% Wald CI | Raw p | Bonferroni p |
| --- | --- | --- | --- | --- | --- | --- | --- |
| p_1 | -1.006925 | 0.365341 | -1.006925 | 0.335666 | [0.189223, 0.705379] | 0.002702 | 0.008105 |
| p_2 | -0.933292 | 0.393257 | -0.933292 | 0.283565 | [0.22558, 0.685571] | 0.000997 | 0.002992 |
| p_4 | -0.253247 | 0.776276 | -0.253247 | 0.291093 | [0.438766, 1.373408] | 0.384308 | 1 |

*Baseline (reference) persona: **p_3**; its coefficient is absorbed by the intercept and is not shown.*

## Raw Counts

| Persona | Initiated (attempts) | Replied (conversations N) | Response rate |
| --- | --- | --- | --- |
| p_1 | 179 | 17 | 9.5 |
| p_2 | 335 | 34 | 10.15 |
| p_3 | 121 | 27 | 22.31 |
| p_4 | 181 | 33 | 18.23 |

## Engagement Depth (Mann-Whitney U)

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
