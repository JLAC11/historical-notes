# Estimación de densidades
La estimación de densidades es parte del [[Unsupervised learning|aprendizaje no supervisado]], con el fin de poder encontrar una estimación de la [[Función de densidad|densidad]].
Históricamente uno de los primeros métodos para estimar las densidades es el de histogramas. Esto surge de querer estimar la [[Función de distribución|función de distribución]].

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

## Histogramas
Suponiendo un conjunto de datos $\mathbf{X}={X_1,...,X_n}\sim^{iid}\mathcal{f}$ donde $\mathcal{f}$ es la densidad de los datos, entonces un histograma es meramente una representación de $\mathcal{f}$ en intervalos discretos:
![[Pasted image 20220223204915.png]]

De otra manera, la altura de cada intervalo medido en el histograma es la proporción de datos en ese intervalo, que va de $x-h/2$ a $x+h/2$ en un intervalo abierto, es decir $(x-h/2,x+h/2)$, donde:
$$\hat{f}(x)=\frac{\mathrm{Altura}}{h}$$
Donde $\hat{f}(x)$ es el estimador de la densidad. Por ejemplo, para la distribución empírica:

$F_n(x) =$ proporción de puntos en $(-\infty,x]$

Utilizando la [[Función indicadora]], sea $K(x)$:
$$K(x) = \mathbb{1}_{(-1/2,1/2)}(x)$$
Entonces:
$$\mathbb{1}_{\{X_i\in(x-h/2,x+h/2)\}}(x) = K\left(\frac{X_i-x}{h}\right)$$

Por lo tanto, el estimador histograma es el siguiente:
$$\hat{f}(x) = \frac{1}{nh}\sum_{i=1}^nK\left(\frac{X_i-x}{h}\right)$$

$$\hat{f}(x) = \frac{1}{nh}\sum_{j=1}^k\mathbb{1}_{(-1/2,1/2)}\left(\frac{x-c_j}{h}\right)\sum_{i=1}^n\mathbb{1}_{(-1/2,1/2)}\left(\frac{x_i-c_j}{h}\right)$$
Donde $n$ es el número de muestras, $h$ es el ancho del estimador, e $i$ es el número de muestras.
***NOTAS:***
1. $\hat{f}(x)\ge 0$
2. $\int_{-\infty}^\infty\hat{f}(x)dx=1$
	1. $\int_{-\infty}^\infty\hat{f}(x)dx=\int_{-\infty}^\infty\frac{1}{nh}\sum_{i=1}^nK\left(\frac{X_i-x}{h}\right)dx$
	2. $\frac{1}{nh}\sum_{i=1}^n\int_{-\infty}^\infty\hat{f}(x)dx=\int_{-\infty}^\infty K\left(\frac{X_i-x}{h}\right)dx$
	3. Si $y=-\frac{1}{h}x$, entonces se obtiene que:
	4. $\frac{1}{n}\sum_{i=1}^n\int_{-\infty}^\infty\hat{f}(x)dx=\int_{-\infty}^\infty K\left(y\right)dy$
	5. $\frac{1}{n}\sum_{i=1}^n1 = 1$
3. Por ley de grandes números: $$\hat{f}(x)=\frac{1}{nh}\sum_{i=1}^nK\left(\frac{X_i-x}{h}\right)\xrightarrow[n\rightarrow\infty]{c.s.}\mathbb{E}\left[K_h(X-x)\right]$$
4. $\mathbb{E}\left[K_h(X-x)\right]=f(x)$?
	1. Por definición del [[Valor esperado]]: $\mathbb{E}\left[K_h(X-x)\right] = \int_{-\infty}^{\infty}K_h(x-y)f(y)dy$
	2. *Definición:* $w$ tiene densidad $\rho$: $$\mathbb{E}[g(w)]=\int_{-\infty}^{\infty}g(w)\rho(w)dw$$
	3. Cuando $h\rightarrow0$ entonces $K_h(x)\rightarrow\delta(x)$ donde $\delta(x)$ es la delta de Dirac, por lo que:
	4. $\lim_{h\rightarrow0}\mathbb{E}\left[K_h(X-x)\right] = \int_{-\infty}^{\infty}\delta_0(x-y)f(y)dy$
	5. $\lim_{h\rightarrow0}\mathbb{E}\left[K_h(X-x)\right] = f(x)$

## Estimador de Parzen-Rosenblatt

Normalmente a este estimador se le llama estimador kernel. Sea entonces el estimador definido de la siguiente manera:

$$\hat{f}_{kernel}(x) = \frac{1}{nh}\sum_{i=1}^{n}K\left(\frac{x-x_i}{h}\right)$$
Donde 
$$K(x) = \mathbb{1}_{(-1/2,1/2)}(x)$$
Y $\mathbb{1}_(a,b)$ es la función indicadora en el intervalo $(a,b)$.
Donde $n$ es el número de muestras, $h$ es el ancho del estimador, e $i$ es el número de muestras.
***NOTAS:***
1. $\hat{f}(x)\ge 0$
2. $\int_{-\infty}^\infty\hat{f}(x)dx=1$
	1. $\int_{-\infty}^\infty\hat{f}(x)dx=\int_{-\infty}^\infty\frac{1}{nh}\sum_{i=1}^nK\left(\frac{X_i-x}{h}\right)dx$
	2. $\frac{1}{nh}\sum_{i=1}^n\int_{-\infty}^\infty\hat{f}(x)dx=\int_{-\infty}^\infty K\left(\frac{X_i-x}{h}\right)dx$
	3. Si $y=-\frac{1}{h}x$, entonces se obtiene que:
	4. $\frac{1}{n}\sum_{i=1}^n\int_{-\infty}^\infty\hat{f}(x)dx=\int_{-\infty}^\infty K\left(y\right)dy$
	5. $\frac{1}{n}\sum_{i=1}^n1 = 1$
3. Por ley de grandes números: $$\hat{f}(x)=\frac{1}{nh}\sum_{i=1}^nK\left(\frac{X_i-x}{h}\right)\xrightarrow[n\rightarrow\infty]{c.s.}\mathbb{E}\left[K_h(X-x)\right]$$
4. $\mathbb{E}\left[K_h(X-x)\right]=f(x)$?
	1. Por definición del valor esperado: $\mathbb{E}\left[K_h(X-x)\right] = \int_{-\infty}^{\infty}K_h(x-y)f(y)dy$
	2. *Definición:* $w$ tiene densidad $\rho$: $$\mathbb{E}[g(w)]=\int_{-\infty}^{\infty}g(w)\rho(w)dw$$
	3. Cuando $h\rightarrow0$ entonces $K_h(x)\rightarrow\delta(x)$ donde $\delta(x)$ es la delta de Dirac, por lo que:
	4. $\lim_{h\rightarrow0}\mathbb{E}\left[K_h(X-x)\right] = \int_{-\infty}^{\infty}\delta_0(x-y)f(y)dy$
	5. $\lim_{h\rightarrow0}\mathbb{E}\left[K_h(X-x)\right] = f(x)$
Suposición: para que pueda estimarse, basta con que $K(x)$ sea una función estimadora tal que cuando su parámetro de anchura tienda a 0 entonces esta converja a una delta de Dirac, o alternativamente: $$\widehat{f}_K(x)\iff\lim_{h\rightarrow_0} \frac{1}{h}K\left(\frac{x-x_0}{h}\right) = \delta(x-x_0)$$
#### Demostración

$$\hat{f}_K(x)\xrightarrow[n\rightarrow\infty]{c.s.}\frac{1}{h}\mathbb{E}\left[K\left(\frac{x-X}{h}\right)\right]$$
Por definición del valor esperado:
$$\frac{1}{h}\mathbb{E}\left[K\left(\frac{x-X}{h}\right)\right] = \frac{1}{h} \int_{-\infty}^{\infty}K\left(\frac{x-X}{h}\right)f(x) dx$$
Entonces, suponiendo que $\lim_{h\rightarrow_0} \frac{1}{h}K(\frac{x-x0}{h}) = \delta(x-x_0)$ y calculando en el límite:
$$\frac{1}{h}\mathbb{E}\left[K\left(\frac{x-X}{h}\right)\right] =\int_{-\infty}^{\infty}\delta(x-X)f(x) dx$$
Entonces:
$$\frac{1}{h}\mathbb{E}\left[K\left(\frac{x-X}{h}\right)\right] = f(x)$$
Y queda demostrado.

### Kernel:
Una función $K:\mathbb{R\rightarrow R}$ es un kernel si: 
$$\int_{\mathbb{R}}K(u)du = 1$$
También es necesario que $K(x) = K(-x)$
#### Ejemplos:
##### Rectangular:
$$K(u) = \frac{1}{2}\mathbb{1}_{(-1,1)}(u)$$
##### Gaussiano:
$$K(u) = \frac{1}{2}\mathbb{1}_{\mathbb{R}}(u)\exp\left(\frac{-u^2}{2}\right)$$
##### Epanechnikov:
$$K(u) = \frac{3}{4}\mathbb{1}_{(-1,1)}(u)(1-u^2)$$
 ##### Biweight:
$$K(u) = \frac{15}{16}\mathbb{1}_{(-1,1)}(u)(1-u^2)^2$$

### Calculando el error cuadrático medio del estimador:
Se calcula como un [[Error cuadrático medio]] cualquiera, dado por la siguiente ecuación:
$$MSE(\hat{f}(x_0)) = \mathbb{V}(\hat{f}(x_0)) + \mathrm{bias}^2 (\hat{f}(x_0))$$
#### Varianza:
Para calcular la varianza, se toma: 
$$\begin{align}
\hat{f}(x_0) &= \frac{1}{n}\sum_{i=1}^n\frac{1}{h}K\left(\frac{x_i-x}{h}\right) \\
&= \frac{1}{n}\sum_{i=1}^n\xi_i
\end{align}$$
Entonces, considerando la varianza de $\xi$:
$$\mathbb{V}(\hat{f}(x_0)) = \frac{1}{n}\mathbb{V}(\xi)$$
Considerando la varianza como la desviación del segundo momento: 
$$\mathbb{V}(\xi) = \mathbb{E}(\xi^2)-\mathbb{E}^2(\xi)\le \mathbb{E}^2(\xi)$$
Por lo tanto: 
$$\mathbb{V}(\hat{f}(x_0))\le  \frac{1}{n}\mathbb{E}^2(\xi)$$
$$\mathbb{V}(\hat{f}(x_0)) = \frac{1}{n}\mathbb{E}(\xi^2)-\mathbb{E}^2(\xi)$$
Que a su vez es:
$$\mathbb{V}(\hat{f}(x_0)) = \frac{1}{n}\int_\mathbb{R}\frac{1}{h^2}K^2\left(\frac{u-x}{h}\right)f(u)du$$

Para que funcione este método, entonces se hace como suposición que: 
1. $f$ es acotada; es decir $f(x)\le f_{max}<\infty$
2. $\int_\mathbb{R}K^2(u)du<\infty$

Debido a que se hace la suposición de que es acotada, entonces se puede hacer lo siguiente:
$$\mathbb{V}(\hat{f}(x_0)) \le \frac{f_{max}}{n}\int_\mathbb{R}\frac{1}{h^2}K^2\left(\frac{u-x}{h}\right)du$$
#TODO

Al final, se obtiene que:
$$\mathbb{V}(\hat{f}(x_0)) \le \frac{f_{max}}{nh}C_1$$
Por lo que si debe encontrarse un $h\rightarrow0$ mientras que $n\rightarrow\infty$, entonces se requiere que el crecimiento de $n$ sea más rápido que lo que $h$ tiende a 0 para que la expresión se encuentre definida.

#### Sesgo

El [[Sesgo|sesgo]] se da por la ecuación:

$$\mathbb{E}\left[\hat{f}(x)\right]-f(x)$$
Recordando: 
$$\mathbb{E}\left[\hat{f}(x)\right] = \mathbb{E}\left[\xi\right]$$

Entonces: 
$$\mathbb{E}\left[\hat{f}(x)\right] = \frac{1}{n}\int_\mathbb{R}\frac{1}{h}K\left(\frac{u-x}{h}\right)f(u)du$$
El sesgo resulta entonces ser:
$$\mathrm{bias}(\hat{f}(x)) = \frac{1}{n}\int_\mathbb{R}\frac{1}{h}K\left(\frac{u-x}{h}\right)f(u)du-f(x)$$

Debido a que $\int_\mathbb{R}K(y)dy = 1$, entonces:

$$\mathrm{bias}(\hat{f}(x)) = \frac{1}{n}\int_\mathbb{R}\frac{1}{h}K\left(\frac{u-x}{h}\right)\left[f(u)-f(x)\right] du$$

Haciendo de cambio de variable $y = \frac{u-x}{h}$, y sacando su [[Serie de Taylor]]:
$$\begin{align}
f(x+yh) &= \sum_{n=0}^\infty \frac{\left(yh\right)^n}{n!}f^{(n)}(x)\left(x+yh-x\right)^n \\
f(x+yh) &= \sum_{n=0}^\infty \frac{1}{n!}f^{(n)}(x)
\end{align}$$

##### Definición de un núcleo de orden $n$:
Se dice que un núcleo o kernel $K$ es de orden $n\in\mathbb{N}$ si:
$$\int u^j K(u)du = 0$$ Para $j= {1,...,n}$

Tomando esta definición, entonces se tiene que: 
$$\begin{align}
\mathrm{bias}(\hat{f}(x)) &= \frac{1}{n}\int_\mathbb{R}\frac{1}{h}K\left(y\right)\left[\sum_{n=0}^\infty \frac{1}{n!}f^{(n)}(x)
-f(x)\right] du \\
\mathrm{bias}(\hat{f}(x)) &= \sum_{i=1}^n f^{(n)}(x)\frac{(hy)^n}{n!}\int_{\mathbb{R}}yK(y)dy
\end{align}$$
Entonces, tomando que $K$ es de orden $n$:
$$\mathrm{bias}(\hat{f}(x)) =\int_\mathbb{R}\frac{(hy)^n}{n!}K(y)\left[f^{(l)}(x+\tau yh) - f^{(l)}(x)\right]dy$$
##### Definición de función de clase Hölder
Una función es [[Condición de Hölder|Hölder]] si tiene derivadas hasta de orden $l=\lfloor{\beta}\rfloor$ y:
$$\left|g^{(l)(x)-g^{l}(x')}\right|\le L\left|x-x'\right|^{\beta-l}$$
Se dice que esta función entonces es Hölder ($\beta,l$).

Entonces, considerando el valor absoluto:
$$\left|\mathrm{bias}(\hat{f}(x))\right| \le \int_\mathbb{R}\frac{(hy)^n}{n!}K(y)\left[f^{(l)}(x+\tau yh) - f^{(l)}(x)\right]dy$$

Suponiendo entonces que $f$ es Hölder $(\beta,n)$:
$$\begin{align}
\left|\mathrm{bias}(\hat{f}(x))\right| &= L \int_\mathbb{R}\frac{\left|hy\right|^n}{n!}\left|K(y)\right|\left|\tau y h\right|^{\beta-l}dy \\
&= h^\beta\frac{L}{n!}\int_{\mathbb{R}}\tau^{\beta-l}\left|y\right|^\beta\left|K(y)\right| dy
\end{align}$$
Suponiendo entonces que este valor: 
$$\frac{L}{n!}\int_{\mathbb{R}}\tau^{\beta-l}\left|y\right|^\beta\left|K(y)\right| dy < C_2 < \infty\Rightarrow \mathrm{bias}^2(\hat{f}(x))\le h^{2\beta}C_2^2$$
Por lo tanto, entonces se tiene que el error cuadrático medio es:
$$MSE(\hat{f}(x)) \le \frac{f_{max}}{nh}C_1+ h^{2\beta}C_2^2$$


#### Corolarios requeridos
1. $f$ acotada, entonces $f\le f_{max}$
2. $\int K^2 (y)dy \le \infty$
3. $f$ es Hölder $(\beta,n)$
4. $K$ es un kernel de orden $n$

Considerando entonces la cota de $h$ para conocer los valores en los que puede encontrarse el óptimo del valor del ancho de banda: 

$$C(h) = \frac{C_1}{nh}+C_2^2h^{2\beta}$$
Tomando su derivada: 
$$C'(h) = -\frac{C_1}{nh^2}+2\beta C_2^2h^{2\beta-1}$$

Optimizando la cota se obtiene entonces:

$$h* = \mathcal{O}n^{-\frac{1}{2\beta+1}}$$

Entonces, la cota se convierte en: 
$$\begin{align}
\mathrm{cota}(h^*) &= \frac{C_1}{nh^*}+\left(C_2h^{*\beta*}\right)^2 \\
&= \frac{C_1}{D}\frac{1}{n}n^{\frac{1}{2\beta+1}}+\frac{C_2^2}{D^2\beta}n^{\frac{2\beta}{2\beta+1}} \\
&= \epsilon n^{\frac{2\beta}{2\beta+1}}

\end{align}$$

Si $\beta\rightarrow\infty$ entonces $\mathrm{cota}(h^*) = \mathcal{O}(n^{-1})$

#### [[Función de pérdida]]

$$\mathbb{E}\left[\int\hat{f}_h^2(x)dx-2\int\hat{f}_h(x)f(x)dx\right]+\int f^2(x)dx$$

Entonces, $$h^*\in\arg\min_{h>0}MISE(h)$$

Por validación cruzada, entonces se tiene:
$$\hat{f}_h^{(-i)}=\frac{1}{(n-1)h}\sum_{j\ne i}K\left(\frac{X_j-x}{h}\right)$$
Sea:
$$\hat{G} = \frac{1}{n}\sum_{i=1}^n\hat{f}_h^{(-i)}(X_i)$$
> Recordatorio:
> $$\mathbb{E}\left(Y(X)\right) = \mathbb{E}_Y\left[\mathbb{E}_{Y|X}\left(Y(X)\right)\right]$$

Entonces:
$$\begin{align}
\mathbb{E}(\hat{G}) &= \mathbb{E}\left[\frac{1}{n}\sum_{i=1}^n\hat{f}_h^{(-i)}(X_i)\right] \\
&= \mathbb{E}_X\left[\hat{f}_h^{(-i)}(X)\right] \\
&=\mathbb{E}_X\left[ \frac{1}{(n-1)h}\sum_{j\ne i}K\left(\frac{X_j-x}{h}\right) \right]  \\

&= \mathbb{E}_X\left[ \frac{1}{(n-1)h}\sum_{j\ne i}\int K\left(\frac{u-x}{h}\right)f(u)du \right] \\
&= \mathbb{E}_X\left[ \frac{1}{h}\int K\left(\frac{u-x}{h}\right)f(u)du \right]
\end{align}
$$

Entonces, tomando a $G$:
$$\begin{align}
G &= \mathbb{E}\left[\int \hat{f}_h(x)f(x)dx\right] \\
&= \mathbb{E}\left[\int \frac{1}{nh}\sum_{i=1}^n K\left(\frac{X_i-x}{h}\right)f(x)dx\right] \\
&= \int \frac{1}{nh}\sum_i \mathbb{E}_X\left[K\left(\frac{X_i-x}{h}\right)\right]f(x)dx \\
&= \frac{1}{h}\int\int K\left(\frac{u-x}{h}\right)f(u)f(x)du\ dx
\end{align}
$$

Tomando $G = \mathbb{E}(\hat{G})$:
$$CV(h) = \int \hat{f}_h^2(x)dx-\frac{2}{n}\sum_{i=1}^n \hat{f}_h^{(-i)}(X_i)$$
Terminando, entonces:
$$h^*_{CV}=\arg\min_{h>0}CV(h)$$

Se hace con el objetivo de estimar el bandwidth $h$

