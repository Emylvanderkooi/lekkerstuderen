# One-Way ANOVA (Analyse van [[Variantie]])
One-Way ANOVA wordt gebruikt om te onderzoeken of de gemiddelden van drie of meer groepen significant van elkaar verschillen.

### Wanneer te gebruiken
- Vergelijken van gemiddelden tussen meerdere onafhankelijke groepen.
- Onderzoek naar het effect van één categorische onafhankelijke variabele (factor) op een afhankelijke variabele.

### Hypotheses
- **Nulhypothese** $(H_0)$: De populatiegemiddelden zijn allemaal gelijk $(\mu_1 = \mu_2 = ... = \mu_I)$.
- **Alternatieve hypothese** $(H_a)$: Niet alle populatiegemiddelden zijn gelijk.

### Assumpties
1. **Onafhankelijke steekproeven** (Simple Random Samples).
2. **Normaliteit**: Scores binnen elke groep zijn normaal verdeeld. 
3. **[[Homoscedasticiteit]]**

### Gerelateerde Formules en Variabelen
- **F-statistiek**: ![[F-statistiek#^formule]]
- **Between-group variance**: ![[Between-Group Variance#^formule-msg]]
- **Within-group variance**: ![[Within-Group Variance#^formule]]
- **Vrijheidsgraden (df)**: ![[Vrijheidsgraden (df)#^df-formules]]
## Voorbeeld van JASP Output voor One-Way ANOVA

Een typische JASP-output voor een One-Way ANOVA ziet er als volgt uit:

| **Bron**   | **SS** | **df** | **MS** | **F** | **p** |
| ---------- | ------ | ------ | ------ | ----- | ----- |
| Groepen    | 18.000 | 2      | 9.000  | 1.446 | 0.278 |
| Error      | 56.000 | 9      | 6.222  |       |       |
| **Totaal** | 74.000 | 11     |        |       |       |

| **Bron**   | **SS**                             | **df**                           | **MS**                            | **F**               | **p** |
| ---------- | ---------------------------------- | -------------------------------- | --------------------------------- | ------------------- | ----- |
| Groepen    | [$SS_G$](Between-Group%20Variance) | [$df_G$](Vrijheidsgraden%20(df)) | [$MSG$](Between-Group%20Variance) | [$F$](F-statistiek) | $p$   |
| Error      | [$SS_E$](Within-Group%20Variance)  | [$df_E$](Vrijheidsgraden%20(df)) | [$MSE$](Within-Group%20Variance)  |                     |       |
| **Totaal** | $SS_T$                             | [$df_T$](Vrijheidsgraden%20(df)) |                                   |                     |       |

### Uitleg van de JASP Output
- **SS (Sum of Squares)**: Meet de variatie tussen de groepen en binnen de groepen.
- **df (Degrees of Freedom)**: Vrijheidsgraden voor de groepen en foutterm.
- **MS (Mean Square)**: Berekening van de variatie door $SS$ te delen door $df$.
  - $MS_{Groepen} = \frac{SS_{Groepen}}{df_{Groepen}} = \frac{18}{2} = 9.000$
  - $MS_{Error} = \frac{SS_{Error}}{df_{Error}} = \frac{56}{9} = 6.222$
- **F-statistic**: Vergelijking van de variatie tussen de groepen ten opzichte van de variatie binnen de groepen.
  $$
  F = \frac{MS_{Groepen}}{MS_{Error}} = \frac{9.000}{6.222} \approx 1.446
  $$
- **p-waarde**: Geeft aan of het resultaat significant is. Hier is de p-waarde $0.278$, wat betekent dat het verschil niet significant is bij een $\alpha$-niveau van $0.05$.

### Voorbeeld
[[One-Way ANOVA Berekening (Handmatig)]]

