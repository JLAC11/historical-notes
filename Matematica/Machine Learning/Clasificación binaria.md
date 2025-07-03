# Clasificación binaria

Es una estrategia de [[Clasificación]], usada solamente cuando hay dos categorías. 

Sea $Y\in\{0,1\}$, y $\eta(X) = \mathbb{P}(Y=1|X)$. Aprovechando que solamente se elige entre 0 y 1, entonces es lo mismo que tomar la [[Distribución de Bernoulli|distribución de Bernoulli]], es equivalente a lo siguiente:
$$\begin{align}
\eta(X) &= \mathbb{P}(Y=1|X) \\ &= \mathbb{E}(Y|X)
\end{align}$$
Debido a que es la misma función de regresión, entonces pueden usarse las mismas estrategias que en clasificación. Sin embargo, debido a que están hechas para regresión, su desempeño será un poco más débil en clasificación. 

El clasificador binario de Bayes entonces es: 

$$g^*(X) = \begin{cases}
1 & \text{si }\eta(X)\ge 1/2 \\
0 & \text{En otro caso}
\end{cases}$$
Y el clasificador óptimo puede ser descrito como: 
$$g^*(X) = \arg\max_{g:\mathcal{X\rightarrow Y}}\mathbb{P}(Y=y|X)$$

Sea $g$ cualquier función $g:\mathcal{X\rightarrow Y}$, entonces: 
$$\begin{align}
\mathbb{P}(g(X)\ne Y|X) &= 1-\mathbb{P}(g(X) = Y|X) \\

&= 1-\left[\sum_{y=0}^1\mathbb{P}(g(X) = y|X) \mathbb{P}(Y= y|X)\right] \\
&= 1-\left[\mathbb{E}(\mathbb{1}_{g(X) = 1}|X)\eta(X) + \left(1-(\mathbb{E}(\mathbb{1}_{g(X) = 0}|X))\right)(1-\eta(X))\right] 
\\
&= 1-\left[\mathbb{1}_{g(X) = 1}\eta(X) + \left(1-\mathbb{1}_{g(X) = 0}(1-\eta(X)\right)\right] 

\end{align}$$
