# Estimador de Nadaraya-Watson

Mucho del desarrollo se basa en [[Estimación de densidades|estimación de densidades]].

Dado este contexto, entonces puede considerarse el estimador de Nadaraya Watson. 
Sea:
$$\left(X_1,Y_1\right),...,\left(X_n,Y_n\right)
\stackrel{iid}{\sim} \left(X,Y\right)$$

Entonces, se puede construir una función de regresión: 
$$m(X) = \mathbb{E}(Y|X)$$
Obteniendo las [[Función de densidad|densidades]] [[Densidad condicional|condicionales]][^1]: 
$$\begin{align}
m(x) &= \int_yyf(y|x)dy \\
&=\int_y y\frac{f(y,x)}{f(x)}dy \\
&= \frac{\int_y yf(y,x)dy}{f(x)}
\end{align}$$
Recordando el estimador de Parzen-Rosenblatt:
$$\hat{f}(x) = \frac{1}{nh}\sum_{i=1}^nK_h(X_i-x)$$
Entonces, se puede estimar a $m(X)$ de la siguiente manera:
$$\hat{m}_h(x) = \frac{\sum_iK_h(X_i-x)\int_\frac{y}{h}yK_h(y_i-y)dy}{\sum_iK_h(X_i-x)}$$
Considerando un kernel de primer orden, entonces se tiene que:
$$\hat{m}_h(x) = \frac{\sum_iK_h(X_i-x)y_i}{\sum_iK_h(X_i-x)}$$




[^1]: Relacionado con [[Ley de probabilidad total]]