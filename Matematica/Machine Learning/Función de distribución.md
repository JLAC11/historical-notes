# Función de distribución
[[Teorema de Glivenko-Cantelli]]
$$F(x) = \mathbb{P}(X\le x)$$

## Densidad
$$f(x) = F'(x)$$
$$f(x) = \lim_{h\rightarrow0}\frac{F(x+h)-F(x)}{h}$$
Entonces, la probabilidad de que los puntos queden en $(x-h/2,x+h/2)=F_n(x+h/2)-F_n(x-h/2)$. Si $n$ es grande:
$$\approx F(x+h/2)-F(x-h/2)$$
Si $h$ es pequeño:
$$\approx F'(x)h=f(x)h$$

Entonces, se da lo siguiente:
$$\begin{align}
X_i\in(x-h/2,x+h/2) &\iff x-h/2<X_i<x+h/2 \\
&\iff h/2<X_i-x<h/2 \\
&\iff 1/2<\frac{X_i-x}{h}<1/2 
\end{align}$$
Utilizando la [[Función indicadora]], sea $K(x)$:
$$K(x) = \mathbb{1}_{(-1/2,1/2)}(x)$$
Entonces:
$$\mathbb{1}_{\{X_i\in(x-h/2,x+h/2)\}}(x) = K(\frac{X_i-x}{h})$$

![[DistribucionFuncion]]

