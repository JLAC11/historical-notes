# Optimización

La optimización de una función se refiere al acto de encontrar un máximo o un mínimo de una función. Un problema de optimización general puede describirse de la siguiente manera:

Optimizar:
$$\min(F(x))\quad o\quad \max(F(x))$$
Sujeto a:
	$$G_i(x) = 0;\quad i = [1,2,\dots,n]$$
	$$H_j(x)\le0\quad j = [1,2,\dots,m]$$
Donde $x$ es un vector de variables.

Para poder resolver uno de estos problemas, basta con que satisfagan las [[Condiciones de Karush-Kuhn-Tucker|condiciones de Karush-Kuhn-Tucker]]
## Métodos duales
TODO 
## Métodos de penalización
Métodos del punto exterior considera una refomulación de la función de penalización exterior
Métodos del punto interior o método de barrera considera una combinación entre función objetivo y conjunto de restricciones con relación logarítmica
## Métodos de linearización parcial

$f(x)$ alrededor de $x_k$:$f(x) = f(x_k)+(x-x_k)\nabla f(x_k) + \frac{1}{2}(x-x_k)^2Hf(x_k)+\dots$
## Métodos de multiplicadores o del lagrangiano aumentado
## Métodos de programación secuencial cuadrática