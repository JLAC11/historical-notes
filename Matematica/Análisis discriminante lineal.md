# Análisis discriminante lineal

[[Clasificador óptimo de Bayes]]

![[Teorema de Bayes]]
Puede describirse como: 
$$\mathbb{P}(Y=k|X=x)=\frac{\mathbb{P}(X=x|Y=k)\mathbb{P}(Y=k)}{\sum_{i=1}^kf_i(x)\mathbb{P}(x=i)}$$
$$\frac{\mathbb{P}(Y=k|X=x)}{\mathbb{P}(Y=j|X=x)}=\frac{f_k(x)}{f_j(x)}\frac{\pi_k}{\pi_j}$$

Considerando el caso: 
$$f_i(x) = \mathcal{N}_p(\mu_i,\Sigma)\quad \forall i; x \subseteq \mathbb{R}^p$$

Entonces, asignamos $Y=\text{Pob}_k$ si $\frac{\mathbb{P}(Y=k|X=x)}{\mathbb{P}(Y=j|X=x)}\ge 1$ 


## LDA
$$Y\in\mathcal{Y}=\{1,...,k\}$$
$$X\in\mathcal{X}\subseteq\mathbb{R}^p$$
Entonces, se busca maximizar: 
$$\mathbb{P}(Y=k|X=x) \propto \mathbb{P}(X=x|Y=k)\mathbb{P}(Y=k)$$
Asignamos $Y=k$ si
$$\frac{f_k(x)}{f_j(x)}\frac{\pi_k}{\pi_j}\ge 1$$
Donde $\pi_i =\mathbb{P}(Y=i)$
### LDA: 
$$X|Y = i \sim \mathcal{N}_p(\mu_i,\Sigma)$$

Describiéndolo en ecuaciones: 

$$\omega_{0k}+\omega_k^Tx \ge \omega_{0j}+\omega_j^Tx \forall j\neq k$$
$$\omega_{0i} = \log\pi_i-\frac{1}{2}\mu_i^T\Sigma^{-1}\mu_i$$
$$\omega_i^T = \mu_i^T\Sigma^{-1}$$

Una manera de estimar sin información a priori es la siguiente: 
$$\widehat{\pi}_1=\widehat{\pi}_2=...=\widehat{\pi}_k = \frac{1}{k}$$
Alternativamente: 
$$\widehat{\pi}_j = \frac{1}{n}\sum_{i=1}^n\mathbb{1}_{Y_{i=j}},\quad j=1,...,k$$

Entonces, estimando el promedio: 
$$\widehat{\mu}_j=\frac{1}{\sum_{i=1}^n\mathbb{1}_{Y_{i=j}}}\sum_{i=1}^nX_i\mathbb{1}_{\{Y_{i}=j\}},\quad j=1,...,k$$
Y la matriz de [[Matriz de covarianza|covarianza]]:
$$\widehat{\Sigma}= \frac{1}{n-k}((n_1-1)S_1+...+(n_k-1)S_k)$$
$$\begin{align}
S_k &= \frac{1}{n_k-1}\sum_{i=1}^n(x_i-\widehat{\mu}_k)(x_i-\widehat{\mu}_k)^T\mathbb{1}_{\{Y_i=k\}} \\
&= \frac{1}{n_k-1}\left[X_k^TX_k-n_k\widehat{mu}_k\widehat{mu}_k^T\right}$$
Y de manera equivalente en matriz: 
$$\widehat{mu}_k=[1,1,...,1]\begin{bmatrix}X_1^T\\ X_2^T\\\vdots\\ X_{nk}^T\end{bmatrix}$$
Que es meramente: 
$$\widehat{mu}_k^T=1_{n_k}^TX_k$$

Sea $J_{nk}=\begin{pmatrix}1 & \hdots & 1 \\ \vdots & \diagdots & \vdots \\ 1&\hdots&1\end{pmatrix}$
![[Pasted image 20220427203449.png]]

### QDA: 
$$X|Y = i \sim \mathcal{N}_p(\mu_i,\Sigma_i)$$


![[Pasted image 20220502204248.png]]