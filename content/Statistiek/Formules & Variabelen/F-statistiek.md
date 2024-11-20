# F-statistiek
De F-statistiek wordt gebruikt om te bepalen of er significante verschillen zijn tussen groepsgemiddelden.

### Formule
$$F = \frac{\text{MSG}}{\text{MSE}} = \frac{\text{MSM}}{\text{MSE}} $$ ^formule

### Uitleg
- **MSG**: Mean Square Groups (variatie tussen groepen) ([[ANOVA]]).
- **MSM**: Mean Square Model (variate tussen variabelen door model).
- **MSE**: Mean Square Error (variatie binnen groepen).

### Toetsing
- Als $H_0$ klopt, volgt de $F$-statistiek een $F(I - 1, N - I)$ verdeling (voor [[ANOVA]]) of een $F(1, n - 2)$ verdeling (voor [[Simple Linear Regression]]).
- Verwerp $H_0$ als de berekende $F$-waarde groter is dan de kritieke waarde of als de p-waarde kleiner is dan het significantieniveau.

