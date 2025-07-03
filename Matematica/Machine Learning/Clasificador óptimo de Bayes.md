# Clasificador óptimo de Bayes

Es un [[Clasificación|clasificador]] que ninguno podrá ser mejor, y es meramente un resultado teórico. 

El error del clasificador óptimo de Bayes también tiene error, pero es quien minimiza la pérdida esperada.
![[LDA]]

## Función de pérdida:
$$g^* \in\arg\min_{g:\mathcal{X\rightarrow Y}} \mathbb{E}_{Y|X}\left[\mathcal{L}(Y,g(X))\right] $$
### Función de pérdida 0-1
$$\mathcal{L}(Y,g(X)) = \mathbb{1}_{g(X)\ne Y}$$

Para poder obtener $g^*$ entonces se requiere la distribución $Y|X$. 



Puede estimarse este valor esperado de la función de pérdida mediante la [[Función de distribución|distribución empírica]]: 

$$\mathbb{E}_{F_n}\left[\mathcal{L}(Y,g(X))\right]= \frac{1}{n}\sum_{i=1}^n\mathcal{L}(Y_i,g(X_I))$$

Existe el problema que no existe una solución única, y que no es un problema bien condicionado, pues cualquier función que cumpla $\forall i,g(X_i)= Y_i$ minimiza la pérdida esperada empírica.

Entonces, para solucionar este problema, se restringe el espacio de búsqueda de $g$; por ejemplo, proponiendo buscarse en una familia de funciones $\mathcal{G}$.

Es decir, minimiza la probabilidad posterior de equivocarse. 


Por ejemplo para regresión logística: 

$$\frac{\mathbb{P}(Y=k|X=x)}{\mathbb{P}(Y=K|X=x)} = x^T\beta_k$$


