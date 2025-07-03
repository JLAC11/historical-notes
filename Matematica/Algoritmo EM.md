# Algoritmo E-M

Algoritmo Expectation-Maximization. Se hace de manera iterativa. 

A veces no se conocen todas las observaciones de un muestreo; por ejemplo, si se determina en modelos de supervivencias suele medirse hasta un tiempo $\tau$, y solo podríamos saber que los datos $X>\tau$.

Asumiendo que los datos completos tienen una densidad conjunta  $f(x;\theta)$ y que los datos observados tienen una densidad conjunta $g(y;\theta)$, y la densidad conjunta de los datos completos una densidad $k(x|y;\theta)$.
Entonces, queremos encontrar los parámetros $\theta$ tales que maximicen $f(x;\theta)$. Si se tiene acceso a las observaciones completas entonces los datos observados no agregan información por lo que, por la ley de probabilidad total: 
$$f(x;\theta) = f(x,y;\theta)=k(x|y;\theta)g(y;\theta)$$
Y 
$$\log f(x,y;\theta) = \log k(x|y;\theta)+ \log g(y;\theta)$$

Pero sin acceso a los datos $x$, solamente los observados $y$, entones se pueden fijar los parámetros a que sean $\phi'$:

En el paso $E$: 
$$\begin{align}
Q(\phi|\phi') &= \mathbb{E}_{x\sim f(\cdot;\phi')}\log g(y;\theta) + \mathbb{E}_{x\sim f(\cdot;\phi')}\log k(x|y;\theta) \\ 
&= \log g(y;\theta) + \mathbb{E}_{x\sim f(\cdot;\phi')}\log k(x|y;\theta)
\end{align}$$
En el paso $M$: se encuentran los parámetros que maximicen $Q(\phi|\phi')$


Entonces, sea $x$ los datos completos y $y$ los datos observados, y que:
$$f(x,y|\theta) = f(x|\theta) = f(x|y,\theta) f(y|\theta)$$

Entonces, la [[Verosimilitud|logverosimilitud]] es la siguiente: 
$$\log f(x|\theta) = \log f(x|y,\theta) + \log f(y|\theta)$$

Supongamos que $X\sim f(x|\theta^{(0)})$, entonces el valor esperado (paso E): 
$$\begin{align}
\mathbb{E}_{X\sim f(x|\theta^{(0)})}\log f(x|\theta) &= \mathbb{E}_{X\sim f(x|\theta^{(0)})}\log f(x|y,\theta)+\log f(y|\theta) \\ &= Q(\theta|\theta^{(0)})\end{align}$$
Y maximizando (el paso M):
$$\theta^{(1)} = \arg\max_{\theta}Q(\theta|\theta^{(0)})$$

### Ejemplo:
Normal con censura por la derecha
![[Censura por la derecha]]

Supongamos que $x_1,...,x_m$ están observados y $x_{m+1}>a,...,x_n>a$ están censurados. 
- Datos observados:
$$y_1=x_1,y_2=x_2,...,y_m=x_m$$
$$y_{m+1}=\{x_{m+1>a}\},y_n=\{x_m>a\}$$
![[Pasted image 20220418202700.png]]

Entonces, la logverosimilitud de la función normal es la siguiente: 
$$\log f(x|\theta) = K -\frac{1}{2}(x-\theta)^2$$
Donde K es una constante. Tomando los datos:
$$\log f(x|\theta) = K -\frac{1}{2}\sum_{i=1}^n(x_i-\theta)^2$$
Considerando los datos observados y los censurados: 
$$\log f(x|\theta) = K -\frac{1}{2}\sum_{i=1}^m(x_i-\theta)^2 - \frac{1}{2}\sum_{i=m+1}^n(x_i-\theta)^2$$
Entonces: 
$$\log f(x|\theta) = K 
-\frac{1}{2} \sum_{i=1}^mx_i^2 
-\frac{1}{2} \sum_{i=m+1}^nx_i^2
-\frac{1}{2} \sum_{i=1}^n\theta^2
+ \theta\left(\sum_{i=1}^mx_i+\sum_{i=m+1}^nx_i\right)$$
En el paso de valor esperado: 

$$Q(\theta|\theta^{(0)}) = K-C - \frac{1}{2}n\theta^2+\theta\mathbb{E}_{X\sim f(x|\theta^{(o)})}\left[ \sum_{i=1}^mx_i+\sum_{i=m+1}^nx_i \right]$$
Para los valores observados: 
$$\mathbb{E}(X_i|Y_i)=\mathbb{E}(X_i|X_i) = X_i, \quad i=1,...,m$$
Entonces, los no observados: 
$$\mathbb{E}(X_j|Y_j) = \mathbb{E}(Z)$$
Donde $Z$ es una distribución normal truncada en $(a,\infty)$ con parámetros $(\theta,1)$:
$$\theta+\frac{\phi(a-\theta)}{1-\Phi(a-\theta)} = \omega_\theta$$
Donde $\phi$ es la densidad  de la distribución normal con media 0 y varianza 1 y $\Phi$ es la distribución normal con media 0 y varianza 1. Entonces, habiendo hecho las cuentas se obtiene que:
$$Q(\theta|\theta^{(0)}) = C_1- \frac{1}{2}n\theta^2+\theta\left[\sum_{i=1}^m{x_i} + (n-m)\omega_{\theta^{(0)}}\right]$$
Maximizando (obteniendo la derivada de $Q$ con respecto a $\theta$):
$$\frac{d}{d\theta}Q(\theta|\theta^{0}=-n\theta + m\bar{x}_{obs}+(n-m)\omega_{\theta^{(0)}}$$

Entonces, obteniendo el argumento del máximo:

$$\theta^* = \frac{m\bar{x}_{obs}+(n-m)\omega_{\theta^{(0)}}}{n}$$
Sustituyendo $\omega_{\theta^{(0)}}$:
$$\theta^* = \frac{m}{n}\bar{x}_{obs} + \frac{n-m}{n}\left(\theta^{(0)}+\frac{\phi(a-\theta^{(0)})}{1-\Phi(a-\theta^{(0)})}\right)$$

Entonces haciéndolo en un solo paso: 
$$\theta^{(j+1)} = \frac{m}{n}\bar{x}_{obs} + \frac{n-m}{n}\left(\theta^{(j)}+\frac{\phi(a-\theta^{(j)})}{1-\Phi(a-\theta^{(j)})}\right)$$

Por el otro lado, puede entenderse tal cual la verosimilitud de la siguiente manera: 

$$\mathcal{L}(\theta|y) \propto \prod_{i=1}^m\phi(x_i|\theta,1)\left(1-\Phi(a-\theta)\right)^{n-m}$$
Debido a que la probabilidad de que $x>a$ es $\Phi(a-\theta)$.