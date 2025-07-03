
Sea $y|\mathcal{N}(X^T,\beta,\sigma^2),\beta\in\mathbb{R}^p$ y suponiendo que se tienen unos datos $\mathcal{D}_n = {(X_1,Y_1),...,(X_n,Y_n)}\sim^{iid}(X,Y)$

$$\mathcal{L}(\beta,\sigma^2) = \frac{1}{\sqrt{2\pi}\sqrt{\sigma^2}}\exp\left[-\frac{1}{2\sigma^2}\sum_{i=1}^n(Y_i-X_i\beta)^T(Y_i-X_i\beta)\right]$$
$$\mathcal{l}(\beta,\sigma^2) = \log{\mathcal{L}(\beta,\sigma^2)} = -\frac{1}{2\sigma^2}\sum_{i=1}^n(Y_i-X_i\beta)^T(Y_i-X_i\beta)-\frac{n}{2}\log{\sigma^2}$$
Sujeto a $\mathbf{K}\beta=m$

Se puede [[Optimización|optimizar]] utilizando un [[Función Lagrangiana|Lagrangiano]], y la función de Lagrange es dada por la siguiente función: 

$$\mathbf{L}(\sigma^2,\beta,l) = -\frac{1}{2\sigma^2}\sum_{i=1}^n(Y_i-X_i\beta)^T(Y_i-X_i\beta)-\frac{n}{2}\log{\sigma^2}-\lambda^T(\mathbf{K}\beta-m)$$
Entonces, maximizando la log[[Verosimilitud|verosimilitud]] deben satisfacerse los siguientes valores:

$$\begin{align*}
\left.\frac{\partial \mathbf{L}}{\partial \beta}\right|_{\hat{\beta},\hat{\sigma}^2,\hat{\lambda}} &= 0 & \left.\frac{\partial \mathbf{L}}{\partial \sigma^2}\right|_{\hat{\beta},\hat{\sigma}^2,\hat{\lambda}} &= 0 & \left.\frac{\partial \mathbf{L}}{\partial \lambda}\right|_{\hat{\beta},\hat{\sigma}^2,\hat{\lambda}} &= 0
\end{align*}$$
       
Obteniéndose los siguientes valores

