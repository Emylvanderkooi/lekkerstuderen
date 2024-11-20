# Inferentie voor Correlatie

### Fisher’s Z-transformatie
De correlatiecoëfficiënt $r$ heeft geen normale verdeling, vooral niet als $\rho \neq 0$. Daarom gebruiken we de **Fisher’s Z-transformatie**:

$$
r_Z = \frac{1}{2} \log \left(\frac{1 + r}{1 - r}\right)
$$

Na de transformatie is $r_Z$ (bij benadering) normaal verdeeld met:
- **Mean**: $\rho_Z = \frac{1}{2} \log \left(\frac{1 + \rho}{1 - \rho}\right)$
- **Standaarddeviatie**: $\frac{1}{\sqrt{n - 3}}$

### Betrouwbaarheidsinterval voor $\rho$
Na transformatie:

$$
CI_{\rho_Z} = r_Z \pm z^* \frac{1}{\sqrt{n - 3}}
$$

Converteer het interval terug naar $\rho$ met de inverse Fisher’s Z-transformatie:

$$
\rho = \frac{e^{2r_Z} - 1}{e^{2r_Z} + 1}
$$
