# Modelos Aditivos Generalizados

Sea la [[Regresión Lineal|regresión lineal]] normalmente descrita de la siguiente manera:

$$y = \beta_0 + \beta_1X^{(1)}+...+\beta_pX^{(p)}+\epsilon$$
Entonces un modelo aditivo generalizado puede describirse de la siguiente manera:
$$y = \beta_0 + f_1(X^{(1)})+...+f_pX^{(p)}+\epsilon$$
O de manera más resumida:
$$y = \sum_jf_j(X^{(j)})+\epsilon$$

Como puede observarse, la clase de modelos descritos por un GAM tiende a ser muy grande, debido a que normalmente el requerimiento de las funciones solamente es que sean infinitamente [[Derivada|diferenciables]], y las posibilidades son muy grandes. 

Tiene como ventajas:
- Buen ajuste
- Muy interpretables
Por ejemplo: 
$$Y\sim \mathrm{Pois}\left(\lambda\left(\sum_jf_j(X^{(j)}\right)\right)$$
$$Y\sim \mathrm{Ber}\left(\lambda\left(\sum_jf_j(X^{(j)}\right)\right)$$

## Enfoque estadístico
De la manera más general, se definen de la siguiente manera:

$$y\sim \mathcal{P}(\mu|X)$$
$$g(\mu|X) = \beta_0+\sum_{i=1}^pf_i\left(X^{(i)}\right)$$
Donde $\mathcal{P}(\mu|X)$ es la distribución de la variable $y$ dado $\mu|X$
Esta representación se valida teóricamente por el [teorema de representación de Kolmogorov-Arnold](https://en.wikipedia.org/wiki/Kolmogorov–Arnold_representation_theorem), con la idea de que cualquier función multivariada puede ser descrita como sumas y composiciones de funciones univariadas. Suponiendo entonces que $g$ sea la función inversa de la función por la que se compondría $\mu|X$, entonces se obtiene esta forma general. 

### Función liga
Función liga // BUSCAR

$g(x) = \log(x)$
