# Regresión Ridge
[[Machine Learning]]


OLS + un parámetro $\lambda$
#TODO 

Se busca minimizar el [[Error cuadrático medio|error cuadrático medio]], es la versión regularizada de [[Regresión Lineal]]

## Traza Ridge
Comparar uno con otro (df vs beta gorrito o lambda vs beta gorrito)


## Adicionales
$$tr(V(\hat{\beta}_R)) = \sigma^2 tr\left[X^TX(X^TX+\lambda I)^{-1}\right]$$
Obteniendo la descomposición SVD:
$$SVD(X^T) = UDV^T$$
Entonces la traza es la siguiente: 
$$\sigma^2\sum_{i=1}^k\frac{d_i^2}{\left(d_i^2+\lambda\right)^2}$$
Donde $d_i$ es el valor singular $i$ de la descomposición
Si $\lambda$ tiende a 0 entonces la traza de la varianza del estimador es $\sum_{i=1}^k\frac{1}{d_i^2}$, y si $\lambda$ tiende a infinito entonces la traza tiende a 0.

## Ajustando el parámetro de Ridge

Sea:
$$\mathbf{\hat{Y}(\lambda) = X}\hat{\beta}_R(\lambda)$$
Y 
$$L(\mathbf{Y,\hat{Y}}) = (Y-\hat{Y}(\lambda))^T(Y-\hat{Y}(\lambda))$$
[Artículo de cómo estimarlo](https://digitalcommons.wayne.edu/cgi/viewcontent.cgi?article=2033&context=jmasm)