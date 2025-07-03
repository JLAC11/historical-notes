
Se refiere a una técnica para hacer una suposición de la distribución dado un conjunto de datos, proponiendo una función $q(x)$ que tenga la siguiente relación: 

$$q(x)\approx p(x|D=d)$$
Es decir, que se asemeje a la [[Ley de probabilidad total|probabilidad]] de x dados los datos d.

Normalmente, para construirlo, se requiere del [[ELBO]], que sirve para describir el límite inferior de la evidencia.

## ¿Por qué surgen los modelos análogos?

A veces, las probabilidades posteriores pueden suponer problemas. Esto, debido a que pueden ser intractables (BUSCAR TRADUCCIÓN)

De manera general, vamos a usar modelos gráficos dirigidos, que tengan  variables $X\in\mathbb{R}^n$ observadas, y variables latentes $Z\in\mathbb{R}^d$ En donde $d$ y $n$ no necesitan ser iguales. 
Entonces, tenemos la probabilidad conjunta $p(X,Z)$ sobre la que queremos realizar inferencias; es decir, observar $X$ y esperar saber algo sobre $Z$

Entonces, queremos la probabilidad posterior, en la que usando el [[Teorema de Bayes]]:
$$p(z|X=D) = \frac{p(X=D|z)p(z)}{p(X=D)}$$
El problema de esta probabilidad posterior, es que puede ser complicado conocer la probabilidad marginal $p(X=D)$. A veces, pueden usarse constantes de normalización, pero no siempre pueden conocerse, ya que de manera general, sobre la medida de $Z$:
$$p(X) = \int_{Z_0} ... \int_{Z_{d-1}}p(X,Z)dZ_0...dZ_{d-1}$$
Y esto no siempre puede ser computado (por ejemplo, si D es muy grande, y es un conjunto de dimensionalidad muy alta)

## Remedio

Entonces, en vez de conocer la verdadera probabilidad posterior, vamos a hacer una inferencia variacional (variacional significando que optimice hacia una función, similar a las técnicas variacionales para los [[Función Lagrangiana|lagrangianos]]) de la siguiente manera: 
$$q(z) \approx p(z|X=D)$$

De tal manera que ambas funciones sean muy similares. 

Para determinar qué tan similares, entonces se requiere de una métrica ([[Divergencia Kullback-Leibler]]), que mida la distancia entre $q$ y $p$.

Entonces, optimizando: 

$$q^*(z) = \arg\min_{q\in \mathcal{Q}}KL\left(q(z)||p(z|X=D)\right)$$

Que es equivalente a reducir la distancia entre $q(z)$ y $p(z|X=D)$ de una familia de distribuciones $\mathcal{Q}$, que de manera general, son más simples que $p(z|X=D)$.

