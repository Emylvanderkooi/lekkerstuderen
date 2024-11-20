# One-Way ANOVA Berekening (Handmatig)

## Gegeven Data

We hebben de volgende data:

| **Groep** | Metingen       |
|-----------|----------------|
| A         | 5, 6, 7, 8    |
| B         | 4, 5, 6, 7    |
| C         | 3, 4, 5, 6    |

---

## Berekening van Groepsgemiddelden en Totaal Gemiddelde

- **Groep A**: $\bar{X}_A = \frac{5 + 6 + 7 + 8}{4} = 6.5$
- **Groep B**: $\bar{X}_B = \frac{4 + 5 + 6 + 7}{4} = 5.5$
- **Groep C**: $\bar{X}_C = \frac{3 + 4 + 5 + 6}{4} = 4.5$
- **Totaal gemiddelde**: $\bar{X} = \frac{5 + 6 + 7 + 8 + 4 + 5 + 6 + 7 + 3 + 4 + 5 + 6}{12} = 5.5$

---

## Berekening van Sum of Squares (SS)

| **Groep** | $y_{ij}$ | $\bar{X}_i$ | $\bar{X}$ | $(y_{ij} - \bar{X})$ | $(\bar{X}_i - \bar{X})$ | $(y_{ij} - \bar{X}_i)$ | $(y_{ij} - \bar{X})^2$ | $(\bar{X}_i - \bar{X})^2$ | $(y_{ij} - \bar{X}_i)^2$ |
|-----------|----------|-------------|-----------|----------------------|-------------------------|------------------------|------------------------|--------------------------|--------------------------|
| A         | 5        | 6.5         | 5.5       | -0.5                | 1.0                     | -1.5                   | 0.25                   | 1.0                      | 2.25                     |
| A         | 6        | 6.5         | 5.5       | 0.5                 | 1.0                     | -0.5                   | 0.25                   | 1.0                      | 0.25                     |
| A         | 7        | 6.5         | 5.5       | 1.5                 | 1.0                     | 0.5                    | 2.25                   | 1.0                      | 0.25                     |
| A         | 8        | 6.5         | 5.5       | 2.5                 | 1.0                     | 1.5                    | 6.25                   | 1.0                      | 2.25                     |
| **B**     | 4        | 5.5         | 5.5       | -1.5                | 0.0                     | -1.5                   | 2.25                   | 0.0                      | 2.25                     |
| B         | 5        | 5.5         | 5.5       | -0.5                | 0.0                     | -0.5                   | 0.25                   | 0.0                      | 0.25                     |
| B         | 6        | 5.5         | 5.5       | 0.5                 | 0.0                     | 0.5                    | 0.25                   | 0.0                      | 0.25                     |
| B         | 7        | 5.5         | 5.5       | 1.5                 | 0.0                     | 1.5                    | 2.25                   | 0.0                      | 2.25                     |
| **C**     | 3        | 4.5         | 5.5       | -2.5                | -1.0                    | -1.5                   | 6.25                   | 1.0                      | 2.25                     |
| C         | 4        | 4.5         | 5.5       | -1.5                | -1.0                    | -0.5                   | 2.25                   | 1.0                      | 0.25                     |
| C         | 5        | 4.5         | 5.5       | -0.5                | -1.0                    | 0.5                    | 0.25                   | 1.0                      | 0.25                     |
| C         | 6        | 4.5         | 5.5       | 0.5                 | -1.0                    | 1.5                    | 0.25                   | 1.0                      | 2.25                     |
| **Totaal**|          |             |           |                      |                         |                        | **SST = 23.0**         | **SSG = 8.0**            | **SSE = 15.0**           |

---

## Berekening van Vrijheidsgraden (df)

- **Between-groups**: $df_G = I - 1 = 3 - 1 = 2$
- **Within-groups**: $df_E = N - I = 12 - 3 = 9$
- **Totaal**: $df_T = N - 1 = 12 - 1 = 11$

---

## Berekening van Mean Squares (MS)

| **Bron**   | **SS** | **df** | **MS**                      | **F**                               |
| ---------- | ------ | ------ | --------------------------- | ----------------------------------- |
| Groepen    | 8      | 2      | $MSG = \frac{8}{2} = 4.0$   | $F = \frac{4.0}{1.67} \approx 2.40$ |
| Error      | 15     | 9      | $MSE = \frac{15}{9} = 1.67$ |                                     |
| **Totaal** | 23     | 11     |                             |                                     |

---

## Berekening van de F-statistic

$$
F = \frac{MSG}{MSE} = \frac{4.0}{1.67} \approx 2.40
$$

### Conclusie
De berekende [[F-statistiek]] is 2.40. Om te bepalen of dit significant is, moeten we deze waarde vergelijken met de kritieke F-waarde uit de F-verdelingstabel voor $df_G = 2$ en $df_E = 9$ bij een gekozen significantieniveau (bijv. $\alpha = 0.05$).

Volgens de calculator is de p-waarde 0.146 dat betekent dat we de nulhypothese niet weggooien.

