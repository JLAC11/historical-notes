Es el límite inferior de evidencia, usado en [[Inferencia variacional]] bayesiana. Se define de la siguiente manera: 

$$\ln p_\theta(x) \ge \mathbb{E}_{z\sim q_\theta}\ln\frac{p_\theta(x,z)}{q_\theta(z)}$$
Donde: 
- $\theta$ son los parámetros que describen a la distribución
- $p_{\theta}(x)$ es la distribución marginal sobre $x$ descrita con parámetros $\theta$
- $q_\theta(x)$ es la [[Surrogate (análogos)|distribución análoga]] a $p_{\theta}(x,z)$
