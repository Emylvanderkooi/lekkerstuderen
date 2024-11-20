# Simple Linear Regression

## Wat is Simple Linear Regression?
**Simple Linear Regression (SLR)** onderzoekt de **relatie** tussen twee **kwantitatieve variabelen**:
- **Response variable (𝑦)** (*afhankelijke variabele*): De uitkomst die we willen voorspellen.
- **Explanatory variable (𝑥)** (*onafhankelijke variabele*): De variabele die de respons beïnvloedt.

### Doelen van Simple Linear Regression
- Beschrijven van de **lineaire relatie** tussen $x$ en $y$.
- Voorspellen van de **gemiddelde waarde** van $y$ op basis van een gegeven waarde van $x$.
- Onderzoeken of er een **statistisch significante associatie** is tussen de variabelen.

---

## Het Model
De lineaire relatie wordt beschreven met de **regressievergelijking**:

$$
\hat{y} = b_0 + b_1x
$$

### Componenten van het model
- **Intercept ($b₀$)**: De voorspelde waarde van $y$ wanneer $x = 0$ (*snijpunt met de y-as*).
- **Slope ($b₁$)**: De verandering in $y$ voor elke eenheid verandering in $x$ (*hellingscoëfficiënt*).
- **Residuals ($eᵢ$)**: Het verschil tussen de **waargenomen waarde ($yᵢ$)** en de **voorspelde waarde ($\hat{y}ᵢ$)**:

  $$
  e_i = y_i - \hat{y}_i
  $$

### Assumpties van het model
1. **Lineariteit**: De relatie tussen $x$ en $y$ is lineair.
2. **Onafhankelijkheid van observaties**.
3. [[Homoscedasticiteit]].
4. **Normaliteit van residuals**: De residuals zijn normaal verdeeld met een gemiddelde van 0.

---

## Ordinary Least Squares (OLS) Methode
**OLS (Kleinste Kwadraten Methode)** wordt gebruikt om de regressielijn te schatten door de **som van de gekwadrateerde residuals** te minimaliseren:

$$
\min \sum_{i} (y_i - \hat{y}_i)^2
$$

### Formules voor het schatten van de parameters
- **Slope ($b₁$)**:
  $$
  b_1 = r \times \frac{SD(y)}{SD(x)}
  $$
- **Intercept ($b₀$)**:
  $$
  b_0 = \bar{y} - b_1 \bar{x}
  $$
  
  Waarbij:
  - $r$ = correlatie tussen $x$ en $y$
  - $SD(x)$ en $SD(y)$ = standaarddeviaties van $x$ en $y$
  - $\bar{y}$ en $\bar{x}$ = steekproefgemiddelden van $y$ en $x$

---
# Inferentie voor Regressie

## [[Betrouwbaarheidsinterval]] voor de Helling ($\beta_1$)
Het [[betrouwbaarheidsinterval]] voor de slope-parameter $\beta_1$ in een regressiemodel wordt berekend als:

$$
b_1 \pm t_{n-2}^* \times SE_{b_1}
$$

- **$t^*$-waarde**: Kritieke waarde uit de $t$-verdeling met $n-2$ vrijheidsgraden.
- **$SE_{b_1}$**: [[Standaardfout (Standard Error)]] van de helling.

### Hypothesetoets voor de Helling
Voor het toetsen van de hypothese:
- **$H_0: \beta_1 = 0$** (geen effect)
- **$H_a: \beta_1 \neq 0$** (wel een effect)

Gebruik de teststatistiek:
$$
t = \frac{b_1}{SE_{b_1}}
$$

Als de berekende $t$-waarde groter is dan de kritieke $t$-waarde, of als de p-waarde kleiner is dan het significantieniveau, verwerp dan $H_0$.

# Voorspellingen in Regressie

We kunnen de resultaten van de regressieanalyse gebruiken voor **voorspellingen**.

## Soorten Voorspellingen
1. **Mean response** voor een subpopulatie bij een bepaalde waarde $x = x^*$:
   - Betrouwbaarheidsinterval (CI) voor de mean response:
$$
\hat{\mu}_y = b_0 + b_1 x^*
$$
 $$
CI_{\hat{\mu}_y} = \hat{\mu}_y \pm t_{n-2}^* \times SE_{\hat{\mu}}
$$

2. **Voorspelling voor een enkele toekomstige waarneming** bij $x = x^*$:
   - Prediction interval (PI) voor een toekomstige waarde:
 $$
\hat{y} = b_0 + b_1 x^*
$$
$$
PI_{\hat{y}} = \hat{y} \pm t_{n-2}^* \times SE_{\hat{y}}
$$

---

## Formules voor het schatten van de Standaardfouten (SE)

### 1. Standaardfout voor de Helling ($b_1$)
$$
SE_{b_1} = \frac{s}{\sqrt{\sum (x_i - \bar{x})^2}}
$$

### 2. Standaardfout voor de Mean Response ($\hat{\mu}_y$)
Voor het schatten van een **mean response** bij $x = x^*$:
$$
SE_{\hat{\mu}} = s \sqrt{\frac{1}{n} + \frac{(x^* - \bar{x})^2}{\sum (x_i - \bar{x})^2}}
$$

### 3. Standaardfout voor een Voorspelling ($\hat{y}$)
Voor het voorspellen van een **toekomstige waarneming** bij $x = x^*$:
$$
SE_{\hat{y}} = s \sqrt{1 + \frac{1}{n} + \frac{(x^* - \bar{x})^2}{\sum (x_i - \bar{x})^2}}
$$

### Uitleg van de termen
- **$s$**: Residual standard error (Root Mean Square Error, RMSE).
- **$n$**: Aantal waarnemingen in de steekproef.
- **$x^*$**: De waarde van $x$ waarvoor we een voorspelling maken.
- **$\bar{x}$**: Het gemiddelde van alle $x$-waarden in de steekproef.
- **$\sum (x_i - \bar{x})^2$**: De som van de gekwadrateerde afwijkingen van $x$ van het gemiddelde.

---

## Verschil tussen CI en PI
- **CI (Confidence Interval)**: Geeft de onzekerheid aan voor het schatten van het gemiddelde responsniveau in een subpopulatie.
- **PI (Prediction Interval)**: Is altijd breder dan een CI omdat het zowel de onzekerheid in het gemiddelde als de variatie van individuele toekomstige waarnemingen meeneemt.

## Belangrijke Notities
- Prediction intervals zijn altijd breder dan confidence intervals vanwege de extra variantie bij het voorspellen van individuele waarnemingen.
- De standaardfouten ($SE$) spelen een cruciale rol in het bepalen van de breedte van deze intervallen.




---

## Analysis of Variance (ANOVA) in Regressie
De **[[ANOVA]]**-tabel wordt gebruikt om te bepalen hoeveel van de variatie in $y$ wordt verklaard door het model.

### Variantiecomponenten
- **SSModel (Sum of Squares Model)**: Verklaarde variatie door het model.
- **SSError (Sum of Squares Error)**: Niet-verklaarde variatie (residuals).
- **SSTotal (Total Sum of Squares)**: Totale variatie in $y$.

  $$
  SSTotal = SSModel + SSError
  $$


![[Determinantiecoëfficiënt#Determinantiecoëfficiënt ($R²$)]]

![[F-statistiek#F-statistiek]]
