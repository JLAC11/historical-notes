# Splines cúbicos suavizados

Imaginando un conjunto de datos, entonces se puede aproximar un conjunto de polinomios que los aproximen, entonces se pueden aproximar construyendo bins o conjuntos y que en los finales (nudos) de cada uno de los conjuntos tanto el valor de la función como su primera derivada (y en principio hasta la derivada n-1) sean iguales para construir una aproximación a la función que lo haga

$$\hat{f} \in\arg\min_{f_\mathcal{X\rightarrow Y}}\sum_{i=1}^n(f(X_i)-Y_i)^2+\lambda\int_\mathcal{X}f''(X)dX$$
Donde $\mathcal{f}$ es un [[Spline|spline]]. Si $\lambda$ es muy grande, entonces se buscará minimizar el valor de la segunda derivada, llevando a un modelo donde sea aproximadamente una recta, y si es muy pequeño, entonces se acerca a la solución por splines cúbicos normales