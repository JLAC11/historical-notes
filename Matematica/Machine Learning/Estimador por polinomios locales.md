# Estimador por polinomios locales

El estimador por polinomios locales va muy relacionado con [[Modelos aditivos generalizados]] y con el [[Estimador de Nadaraya-Watson]].

Suponiendo que un proceso pueda ser descrito: 
$$\mathbb{E}(Y|X) = m(X)$$
Obtieniendo un polinomio de [[Serie de Taylor|Taylor]] alrededor de un punto $x_0$:
$$m(x)\approx \sum_{k=0}^p\frac{1}{k!}m^{(k)}(x_0)(x-x_0)^k$$
Entonces puede estimarse de la siguiente manera:
$$m(x) = \sum_{k=0}^p\beta_k(x-x_0)^k$$
Es decir, estamos haciendo [[Regresión Lineal]] sobre la base $\left(1,x-x_0,(x-x_0)^2,...,(x-x_0)^p\right)$

Si $p=1$, entonces:
$$m(x) \approx \beta_0+\beta_1(x-x_0)$$
Y pueden hacerse mínimos cuadrados, pero por el otro lado, pueden hacerse mínimos cuadrados ponderados, con el uso de un kernel con la siguiente función de pérdida:
$$\mathcal{L}' = \sum_i\left(Y_i-\beta_0-\beta_1(x_i-x_0)^2\right)K_h(x_i-x_0)$$
Entonces, obteniendo una matriz de diseño centrada alrededor de $x_0$:
$$\mathbf{X}_{x_0}=
\left[\begin{matrix}
1 & x_1-x_0 \\
1 & x_2-x_0 \\
\vdots & \vdots \\
1 & x_n-x_0 \\
\end{matrix}\right]$$
Y sea $\mathcal{W_{x_0}}$ una matriz de pesos:
$$\mathcal{W}_{x_0}=
\left[\begin{matrix}
K_h(x_1-x_0) & & \\
& ... & \\
& & K_h(x_n-x_0)\\
\end{matrix}\right]$$
Entonces, se puede plantear de la siguiente manera:
$$(Y-\mathbf{X}_{x_0}\beta)^T\mathcal{W_{x_0}}(Y-\mathbf{X}_{x_0}\beta)$$

Entonces, multiplicando por $\mathcal{W_{x_0}}^{\frac{1}{2}}$ por ambos lados:
$$(\mathcal{W_{x_0}}^{\frac{1}{2}}Y-\mathcal{W_{x_0}}^{\frac{1}{2}}\mathbf{X}_{x_0}\beta)^T(\mathcal{W_{x_0}}^{\frac{1}{2}}Y-\mathcal{W_{x_0}}^{\frac{1}{2}}\mathbf{X}_{x_0}\beta)$$

Entonces, la solución para el estimador por mínimos cuadrados es la siguiente:
$$\hat{\beta} = \left(\mathbf{X}_{x_0}^T\mathcal{W_{x_0}}\mathbf{X}_{x_0}\right)^{-1}\left(\mathbf{X}_{x_0}^T\mathcal{W_{x_0}}Y\right)$$


Condiciones:

$$y=m(x)+\epsilon$$
$\epsilon_1,...,\epsilon_n$ son independientes con $\mathbb{E}(\epsilon_i)=0$; $\mathbb{E}(\epsilon_i^2)\le\sigma^2_{max}<\infty$ 
Que $m(x)\in \text{Hölder}(\beta,l)$ y además $\left|\text{bias}\right|\le \frac{C_1L}{l!}h^\beta$, $\text{Var}\le \frac{\sigma_{max}^2C_2^2}{nh}$

