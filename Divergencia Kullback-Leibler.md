La divergencia de Kullback-Leibler se define de la siguiente manera: 

$$KD(P||Q) = \int_{x\in\mathcal{X}}P(x)\log\frac{P(x)}{Q(x)}dx$$

Para dos [[Función de densidad|funciones de densidad]] $P(X)$, $Q(X)$.

Alternativamente, puede entenderse como la entropía relativa de $P(X)$ en $Q(X)$

La divergencia no es una métrica, ya que, de manera general, $KD(P||Q) \neq KD(Q||P)$.

En [[Machine Learning]], también es conocido como ganancia de información

## Definición en términos de valor esperado: 

La distancia de Kullback-Leibler es equivalente al valor esperado del logaritmo del odds-ratio: 

$$KD(P||Q) = \mathbb{E}_{p(x)}\left[\frac{q(x)}{p(x)} \right]$$