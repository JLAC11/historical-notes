# Clasificación
Cae dentro del [[Supervised learning|aprendizaje supervisado]]. 
Entonces, sean las variables predictoras $X\in\mathcal{X}\subseteq \mathbb{R}^p$ y las variables a clasificar $Y\in\mathcal{Y}=\{1,...,M\}$
Deseamos el mejor clasificador que minimice alguna [[Función de pérdida|función de pérdida]]:
$$\mathcal{L}:\mathcal{X}\times\mathcal{Y}\rightarrow\mathbb{R}^+$$
Es decir, buscamos que minimice:
$$\mathcal{L}\left(Y,g(X)\right)$$
Para que esté bien definido el problema tomamos el valor esperado:
$$g^* \in \arg \min_{g:\mathcal{X\rightarrow Y}} \mathbb{E}_{Y|X}\left[\mathcal{L}(Y,g(X))\right]$$
En este caso, $g^*$ es llamado el clasificador óptimo de Bayes.
### ¿Qué función de pérdida usar?

Si ningún error de clasificación es peor que otro: 
$$\mathcal{L}(Y,g(X)) = \mathbb{1}_{g(X)\ne Y}$$

Esta función de pérdida es llamada la función de pérdida 0-1. 
$$\mathbb{E}_{Y|X}\left[\mathcal{L}(Y,g(X))\right] = \mathbb{E}_{Y|X}\left[\mathbb{1}_{g(X)\ne Y}\right]
$$
Debido a que esta función de pérdida meramente puede tomar valores 0 y 1, entonces es una distribución de Bernoulli, o puesto de otra forma: 
$$\mathbb{E}_{Y|X}\left[\mathbb{1}_{g(X)\ne Y}\right] = \mathbb{P}\left(g(X)\ne Y|X \right)$$
Por lo que se tiene como función de pérdida: 
$$g^* \in \arg \max_{g:\mathcal{X\rightarrow Y}} \mathbb{P}\left(g(X) = Y|X \right)$$

Sin embargo, $g^*$ no se puede obtener si se desconoce la distribución de $Y|X$. Por lo tanto, recurrimos a datos $\mathcal{D}_n=((X_1,Y_1),...,(X_n,Y_n))$
Donde $(X_i,Y_i)\stackrel{iid}{\sim}(X_n,Y_n)$

El objetivo será construir a partir de $\mathcal{D}_n$ un clasificador $g_n:\mathcal{X\rightarrow Y}$ tal que:
$$\begin{align}
g_n&\in \arg \min_{g:\mathcal{X\rightarrow Y}} \mathbb{E}_{F_n}\left[\mathcal{L}(Y,g(X))\right]\\
&= \frac{1}{n}\sum_{i=1}^n\mathcal{L}(Y_i,g(X_i))
\end{align}$$
Si se usa la función indicadora, entonces:
$$\frac{1}{n}\sum_{i=1}^n\mathbb{1}_{g(X_i)\ne Y_i}$$

Si no son IID entonces hay que recurrir a causalidad :(


Otra posible es la curva [ROC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic), a la que se toma el área bajo su curva. 
![[ROCCurve]]

El mejor clasificador es el [[Clasificador óptimo de Bayes]].



| Regresión        | Clasificación                 |
| ---------------- | ----------------------------- |
| $Y\in\mathbb{R}$ | $Y\in\mathcal{Y}=\{1,...,M\}$ |
| $\mathbb{P}(Y=y  \| X) = 0$                       | $\mathbb{P}(Y=y \| X) \ge 0$ |

### Teorema 2.1 (Devroye, Györfi,Lugosi)
