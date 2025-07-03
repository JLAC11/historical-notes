# Derivada conformable

La derivada conformable, según [Akkurt](https://www.researchgate.net/publication/316015090_A_new_Generalized_fractional_derivative_and_integral) se define de la siguiente manera:

$$D^\alpha f(t) := \lim_{\varepsilon\rightarrow0}\frac{f\left(t-k(t)+k(t)\exp\left(\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}\right)\right)-f(t)}{\varepsilon}$$

Donde $k(t)$ sea una función estrictamente creciente, continua, diferenciable y positiva en todo su dominio, tal que $k(t),k'(t)>0,\ \ \forall t>0$, y $0<\alpha\le1$. Si el límite existe, entonces se dice que la función es $\alpha$-diferenciable. Requisito: la función k/k cuando alfa es 1 debe ser 1

### Teorema 1. 
$$f^{(\alpha)}(t)=D^\alpha f(t) = \frac{k^{1-a}(t)}{k'(t)}f'(t)$$
#### Demostración
De la definición se tiene que:
$$D^\alpha f(t) := \lim_{\varepsilon\rightarrow0}\frac{f\left(t-k(t)+k(t)\exp\left(\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}\right)\right)-f(t)}{\varepsilon}$$
Sustituyendo con la [[Serie de Taylor|serie de Taylor]], expandida en $\epsilon\rightarrow0$:
$$\exp\left(\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}\right) = 1+\left(\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}\right)+\frac{\left(\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}\right)}{2!}+\dots$$
$$\exp\left(\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}\right)=\sum_{n=0}^{\infty}\frac{\left(\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}\right)^n}{n!}$$
$$\exp\left(\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}\right)=1+\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}+O(\varepsilon^2)$$
$$D^\alpha f(t) := \lim_{\varepsilon\rightarrow0}\frac{f\left(t-k(t)+k(t)\left(1+\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}+O(\varepsilon^2)\right)\right)-f(t)}{\varepsilon}$$
Distribuyendo el producto:
$$D^\alpha f(t) := \lim_{\varepsilon\rightarrow0}\frac{f\left(t+\varepsilon\frac{k(t)^{1-\alpha}}{k'(t)}\left(1+O(\varepsilon)\right)\right)-f(t)}{\varepsilon}$$
Sea $h=\varepsilon\frac{k(t)^{1-\alpha}}{k'(t)}\left(1+O(\varepsilon)\right)\Rightarrow \varepsilon =\frac{h}{\frac{k(t)^{1-\alpha}}{k'(t)}\left(1+O(\varepsilon)\right)}$
Entonces:
$$D^\alpha f(t) := \lim_{\varepsilon\rightarrow0}\frac{k(t)^{1-\alpha}}{k'(t)}\left(1+O(\varepsilon)\right)\lim_{h\rightarrow0}\frac{f\left(t+h\right)-f(t)}{h}$$
$$D^\alpha f(t) := \lim_{\varepsilon\rightarrow0}\frac{f\left(t-k(t)+k(t)\exp\left(\varepsilon\frac{k(t)^{-\alpha}}{k'(t)}\right)\right)-f(t)}{\varepsilon}.$$
Con esto concluye la demostración. $\blacksquare$


### Teorema 2.
Si $\alpha\rightarrow1$ y $k(t)=t$, entonces la derivada es la definición clásica de la [[Derivada|derivada]].
#### Demostración

Tomando la derivada de $k(t)$:
$$k'(t)=1$$
Entonces:
$$\lim_{\alpha\rightarrow1}D^\alpha f(t) = \lim_{\alpha\rightarrow1}\frac{k^{1-a}(t)}{k'(t)}f'(t)$$
Sustituyendo $k(t)$ y $k'(t)$:
$$\lim_{\alpha\rightarrow1}D^\alpha f(t) = \lim_{\alpha\rightarrow1}t^{1-a}f'(t)$$
$$D^1f(t) = Df(t)=t^0f'(t)=f'(t)\forall t>0.$$
Con esto concluye la demostración. $\blacksquare$

### Teorema 3
$D^\alpha f(t) = f'(t)$ si $k(t) = \left(\alpha(t+c)\right)^{\frac{1}{\alpha}},\forall c\ge0$

#### Demostración
$D^\alpha f(t) = f'(t)$ si $\frac{k(t)^{1-\alpha}}{k'(t)}=1$
Entonces, se cumple esto cuando se resuelve la ecuación diferencial.
Resolviendo la ecuación diferencial:
$$k'(t) = k(t)^{1-\alpha}$$
Separando variables:
$$k(t)^{\alpha-1}k'(t) = 1$$
Integrando:
$$\int_0^tk(t)^{\alpha-1}k'(t)dt=\int_0^tdt$$
Sea $u=k(t)\Rightarrow du = k'(t)dt$, entonces:
$$\int u^{\alpha-1}du=\int_0^tdt$$
$$\frac{1}{\alpha}u^\alpha+C = t$$
Sustituyendo $u=k(t)$ y despejando:
$$k(t)^\alpha=\alpha\left(t-C\right)$$
$$k(t)=\left(\alpha\left(t-C\right)\right)^\frac{1}{\alpha}$$
Debido a que $c$ es una constante, entonces sustituyendo $c=-C$:
$$k(t) = \left(\alpha(t+c)\right)^{\frac{1}{\alpha}}$$
Con esto se cumple la primera parte del teorema. Para demostrar que $c>0$, se recuerda de la definición que tanto $k(t)$ como $k'(t)$ deben ser mayores que 0. 

Recordando que $0<\alpha<1$, entonces $\frac{1}{\alpha}>1$. 
Obteniendo la derivada:
$$k'(t) = \frac{1}{\alpha}\left(\alpha(t+c)\right)^{\frac{1}{\alpha}-1}$$
Se encuentra un máximo, mínimo o punto de inflexión en cuanto la derivada sea 0, por lo que si existe un punto crítico de este estilo, puede saberse que entonces la derivada fue menor que 0 antes o después, si es un máximo o mínimo (rompiendo el requerimento que  $k(t),k'(t)>0$), o $k(t)<0$ si es un punto de inflexión. Evaluando este punto crítico:

$$\frac{1}{\alpha}\left(\alpha(t+c)\right)^{\frac{1}{\alpha}-1}=0$$
$$\left(\alpha(t+c)\right)^{\frac{1}{\alpha}-1}=0$$
$$\alpha(t+c)=0$$
$$t=-c$$
Si el punto crítico se encuentra en $t=-c$, y $t>0$, si $c<0$ entonces se encuentra el punto crítico en donde $t>0$, por lo que no se cumpliría el requerimento de  $k(t),k'(t)>0$. Por lo tanto, $c\ge 0$. Con esto concluye la demostración. $\blacksquare$
#### Observaciones
En el caso limitante que $\alpha\rightarrow0$, puede observarse que el kernel meramente está siendo operado con la [[Derivada logarítmica|derivada logarítmica]], y cuando $\alpha\rightarrow1$, se tiene la división de $\frac{f'(t)}{k'(t)}$, donde si se aplica el límite, se obtiene $\frac{df}{dk}$.
Este resultado es relevante porque marca el punto en el cual el [[Kernel|kernel]] de la derivada conformal pasa a crecer más o menos rápidamente que una derivada ordinaria. Si el kernel es menor que esta función limitante $\forall t>0$, entonces la derivada conformal crece más rápido que la ordinaria, y el converso también es cierto.



### ¿Es un difeomorfismo?
Para que la derivada conformable de Akkurt sea un [[Difeomorfismo|difeomorfismo]], se requiere que el mapeo $D^\alpha:\mathcal{f}\rightarrow\mathbb{R}$ sea invertible y diferenciable. 
Recordando el kernel de la transformación:
$$D^\alpha f(t) = \frac{k^{1-a}(t)}{k'(t)}f'(t)$$
Donde $k(t)$ es una función continua, diferenciable, no negativa y estrictamente creciente, y $0<\alpha\le1$. Sin embargo, estas condiciones no son suficientes para poder hacer la derivada conformable de Akkurt en un difeomorfismo. Para demostrarse, puede tomarse un ejemplo muy sencillo. 
Sea $g(t) = k'(t)$ definida de la siguiente manera:
$$
g(t) = \begin{cases} 0.1t & 0\le t \le 1\\t-0.9 & 1<t\end{cases}
$$
Entonces 
$$k(t) = \int_0^tg(x)dx$$
Puede verse que esta función cumple con los requisitos de que $k(t)$ sea diferenciable, no negativa, y estrictamente creciente para todo el intervalo en el que está definida, y que $k'(t)$ es continua  y positiva en todo su dominio, por lo que acorde a la definición de Akkurt, es un núcleo adecuado. Sin embargo, el núcleo de la transformación no es invertible, debido a que no es biyectivo. Puede demostrarse que no es biyectivo ya que el núcleo presenta por lo menos un mínimo local. Además, no es diferenciable en todo el dominio, por lo que no puede ser un difeomorfismo. 
Para demostrar que no es diferenciable en todo el dominio, se encuentran los límites de la derivada de la función en ambos lados de cuando la función se evalúa en 1:
$$N(t) = \frac{k^{1-a}(t)}{k'(t)}$$
$$N(t) = 
\begin{cases}
\frac{\left(0.1\tfrac{t^2}{2}\right)^{1-\alpha}}{0.1t} & 0\le t\le 1 \\
\frac{\left(t\left(\tfrac{t}{2}-0.9\right)\right)^{1-\alpha}}{t-0.9} & 1<t \end{cases}
$$
Sin pérdida de generalidad, considerando las constantes:
$$N(t) = 
\begin{cases}
\beta t^{1-2\alpha} & 0\le t\le 1 \\
\frac{\left(t\left(\tfrac{t}{2}-0.9\right)\right)^{1-\alpha}}{t-0.9} & 1<t 
\end{cases}
$$
# General
$$
D^\alpha f(t)=\phi(t,\alpha)f'(t)
$$
- Inyectiva en $\alpha$
- Cuando $\lim_{\alpha\rightarrow1}D^\alpha f(t)=f'(t)$
- $\lim_{\alpha\rightarrow0}\phi(t,\alpha)f(t) = f(t)$
- $\phi(t,\alpha)$ es positiva

***NOTA:*** Se considera que $t \in \mathbb{C}|\Re(t)>0$
## Demostraciones que si cumple esto entonces tiene propiedades normales para cálculo
### Linealidad
Si se aplica a dos funciones complejas: 
$$D^\alpha(f(z)+g(z)) = D^\alpha f(z) + D^\alpha g(z)$$
Fácil observar; si se sustituye en cómo se define, y usando la propiedad asociativa de la multiplicación en los complejos se obtiene:
$$\begin{align*}
D^\alpha(f(z)+g(z)) &= \phi(z,\alpha)\left[f'(z)+g'(z)\right] \\
D^\alpha(f(z)+g(z)) &= \phi(z,\alpha)f'(z) +\phi(z,\alpha)g'(z)
\end{align*}$$
### Regla de la cadena:
$$D^\alpha(f(g(z))) = \phi(z,\alpha)\left[f(g(z))\right]'$$
Debidoa que la derivada no actúa sobre el núcleo de la transformación, se obtiene lo siguiente: 
$$D^\alpha(f(g(z))) = \phi(t,\alpha)f'(g(z))g'(z)$$
### Regla del producto 
Se cumple igual, debido a que meramente se multiplica por un kernel. 

### Integrando:
$$\int_{\gamma}D^\alpha f(z) dz$$
Supongamos que $\gamma$ es una curva (no cerrada), entonces, usando la regla del producto para una derivada común; 

$$\begin{align*}
\int_{\gamma}D^\alpha f(z) dz &= \int_\gamma\phi(z,\alpha)f'(z)dz \\
&=\left.\phi(z,\alpha)f(z)\right|_\gamma -\int_\gamma f(z)\frac{\partial}{\partial z}\phi(z,\alpha)dz
\end{align*}$$
Parametrizando:

$$\int_\gamma D^\alpha f(z) dz=\left.\phi(\gamma(t),\alpha)f(\gamma(t))\gamma'(t)\right|_{t_0}^{t_1} -\int_\gamma f(z)\frac{\partial}{\partial z}\phi(z,\alpha)dz
$$
NOTA: se hace la suposición de que $\phi(z,\alpha)$ es diferenciable en $z$, pero si es diferenciable por pedazos, puede extenderse sin tanta dificultad

### Conformabilidad

Sea $\gamma$ una curva suave, donde $\theta$ es tangente a la derivada conformal $\phi(\gamma,\alpha)f(\gamma)$ en $z_0$ y $\omega$ a $\gamma$ en $z_0$ y $w_0$ en el plano complejo, entonces:
$$\begin{align}
w-w_0&\equiv \phi(z,\alpha)f(z)-\phi(z_0,\alpha)f(z_0)\\
w-w_0&=\frac{\phi(z,\alpha)f(z)-\phi(z_0,\alpha)f(z_0)}{z-z_0}(z-z_0)

\end{align}$$

Tomando el argumento:
$$\begin{align}
\arg(w-w_0) &= \arg\left(\frac{\phi(z,\alpha)f(z)-\phi(z_0,\alpha)f(z_0)}{z-z_0}(z-z_0)\right) \\
&=\arg\left(\frac{\phi(z,\alpha)f(z)-\phi(z_0,\alpha)f(z_0)}{z-z_0}\right) + \arg(z-z_0)
\end{align}$$
Que, entonces, cuando se toma el límite cuando $z\rightarrow z_0$ y $w\rightarrow w_0$, entonces:
$$\begin{align}
\theta  &=\arg\left(\left[\phi(z,\alpha)f(z)\right]'\right) + \omega \\
&= \arg\left(\phi'(z,\alpha)f(z)+\phi(z,\alpha)f'(z)\right)+\omega
\end{align}$$
Y:
$$|w|=\left|\phi'(z,\alpha)f(z)+\phi(z,\alpha)f'(z)\right||z|$$
Donde se entiende que $\phi'(z,\alpha)=\frac{\partial}{\partial z}\phi(z,\alpha)$

Sea entonces $\phi((x,y),\alpha) = a((x,y),\alpha)+ib((x,y),\alpha)$ y $f(x,y) = u(x,y)+iv(x,y)$ donde $z=(x+iy)$

## Posibilidad? 
Suponiendo entonces que sea para una variable compleja: 
$$\lim_{h\rightarrow0}\frac{f(z-\phi(t,\alpha)(1-\exp\left(-h\right)))}{h}$$

Resolver ecuación diferencial de primer orden con esta derivada, que sea lineal y con coeficientes constantes primero, y después con coeficientes variables 

Puede ser tal cual o separando en parte imaginaria y real.

Para $z\in\mathbb{C}$:

### Caso 1
$$D^\alpha f(z) = bf(z)$$

Entonces:
$$\phi(z;\alpha) f'(z) = bf(z)$$
Por lo tanto:
$$\frac{f'(z)}{f(z)} = \frac{b}{\phi(z;\alpha)}$$
Restringiéndonos en primera instancia para una variable $z\in\mathbb{R}$, y tomando el límite de la función cuando tiende a 0:
$$\begin{align}
\lim_{t_0\rightarrow0}\int_{t_0}^t\frac{f'(z)}{f(z)}dz & = \lim_{t_0\rightarrow0}\int_{t_0}^t\frac{b}{\phi(z;\alpha)}dz \\
\lim_{t_0\rightarrow0}\ln{\frac{f(t)}{f(t_0)}} &= \lim_{t_0\rightarrow0} \int_{t_0}^t\frac{b}{\phi(z;\alpha)}dz \\
f(t) &= \lim_{t_0\rightarrow0}f(t_0)\exp\left(\int_{t_0}^t\frac{b}{\phi(z;\alpha)}dz\right)
\end{align}$$
Ahora, extendiendo esta solución a $z\in\mathbb{C}$, debe encontrarse si la función del lado derecho es multivaluada u holomórfica, 
Existen polos para la función cuando $\phi(z;\alpha)=0$

### Caso 2
$$D^\alpha f(z) = bf(z) + c$$
Separando variables e integrando, primero suponiendo que la trayectoria es en $\mathbb{R}^+$ y es una trayectoria abierta: 
$$\begin{align}
\phi(z;\alpha) f'(z) &= bf(z)+c \\
\frac{f'(z)}{bf(z)+c} &= \frac{1}{\phi(z;\alpha)} \\
\int_{\gamma}\frac{f'(z)}{bf(z)+c}dz &= \int_{\gamma}\frac{1}{\phi(z;\alpha)}dz \\
\left.\ln\left(bf(z)+c\right)\right|_{z_0}^z &= \int_{\gamma}\frac{1}{\phi(z;\alpha)}
\end{align}$$

! CONSIDERAR POR VARIACION DE PARAMETROS 
#### Considerando variación de parámetros: 
Se tiene la solución del caso 1:
$$f(t)= \lim_{t_0\rightarrow0}f(t_0)\exp\left(\int_{t_0}^t\frac{b}{\phi(z;\alpha)}dz\right)$$

Proponiendo entonces una variación de parámetros de la siguiente manera: 
$$f_p(t) = P(t)f(t)$$
Obteniendo la derivada por regla del producto:

$$D^\alpha f_p(t) = \left[D^\alpha P(t)\right]f(t) + P(t)[D^\alpha f(t)]$$

Sustituyendo en la ecuación: 
$$\begin{align}
D^\alpha f_p(z) &= bf_p(z) + c \\
\left[D^\alpha P(t)\right]f(t) + P(t)[D^\alpha f(t)]&= bP(t)f(t) +c \\
P(t)\left[D^\alpha f(t)-bf(t)\right] + f(t)D^\alpha P(t) &= c \\
P(t)\left[D^\alpha f(t)-bf(t)\right] &= c - f(t)D^\alpha P(t) 

\end{align}$$
Tomando la solución homogénea, cuando $D^\alpha f(t) = bf(t)$, entonces el término del lado izquierdo de la ecuación es cero. Por lo tanto:
$$\begin{align}
f(t)D^\alpha P(t) &= c \\
f(t)\phi(t;\alpha) P'(t) &= c \\
P'(t)  &= \frac{c}{f(t)\phi(t;\alpha)}
\end{align}$$

Integrando con respecto a $t$, entonces: 
$$P(t) = \int_{t_0}^t \frac{c}{f(t)\phi(t;\alpha)}dt $$

Entonces, la solución a la ecuación diferencial es la siguiente:
$$f_p(t) = f(t)P(t) = f(t)\int_{t_0}^t \frac{c}{f(t)\phi(t;\alpha)}dt$$
A su vez, del hecho que $f(t) = f(t_0)\exp\left(\int_{t_0}^t\frac{b}{\phi(z;\alpha)}dz\right)$: 
$$f_p(t) = f(t)P(t) = f(t_0)\exp\left(\int_{t_0}^t\frac{b}{\phi(z;\alpha)}dz\right)\int_{t_0}^t \frac{c}{f(t_0)\exp\left(\int_{t_0}^t\frac{b}{\phi(z;\alpha)}dz\right)\phi(t;\alpha)}dt$$


### Caso 3
$$D^\alpha f(z) = g(z)$$
Integrando para obtener una solución:
$$\phi(z;\alpha) f'(z) = g(z)$$
$$ \int_\gamma f'(z) dz = \int_\gamma \frac{g(z)}{\phi(z;\alpha)} dz$$

[Encontré un caso que ya se usan](https://faculty.cord.edu/andersod/p108_orig.pdf)

### Caso 4
$$D^\alpha f(z) = g(z)f(z)+h(z)$$


# Caso conmesurado

Sea $\mathrm{D}^\alpha$ el siguiente operador diferencial: 
$$\mathrm{D}^\alpha = \begin{bmatrix}\kappa_0(\alpha,t)\\\kappa_1(\alpha,t)\frac{d}{dt}\\\vdots\\ \kappa_p(\alpha,t)\frac{d^p}{dt^p}\end{bmatrix}$$
Y sea aplicado a una función 
$$\mathrm{D}^\alpha f(t) = \sum_{i=0}^p\kappa_if^{(i)}(t)$$
# Caso no conmesurado 
$\alpha$s diferentes

## Tags
#Matemáticas
