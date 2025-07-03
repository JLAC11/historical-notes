# Derivada conformable aplicada
## Aplicación 1
Sea $T:\mathbb{R}\times\mathbb{R}^+\rightarrow\mathbb{R}^+$, tal que $T(x,t); x\in \mathbb{R};\quad t\in\mathbb{R^+}$. Sea el operador diferencial $D^\alpha=\kappa_0(\alpha,x)\frac{d}{dx}$, y sea el siguiente problema de transporte de calor en el cuerpo de un sólido:
Transporte de calor: 
$$k\frac{\partial T}{\partial z} = h(T_\infty-T)$$
En términos adimensionales: 
$$-\frac{\partial \theta}{\partial \xi} = \text{Bi}_h\theta$$
$$\text{Bi}_h = \frac{hL}{k}$$
$$h = \text{Re}^\alpha\text{Pr}^\beta\left(\frac{\mu}{\mu_w}\right)^\gamma$$
$$\text{Re}(x) = \frac{\rho v(x)D}{\mu}$$
$$h = h(\alpha,x) = C\text{Re}(x)^\alpha$$
Por cambio de variable, se sabe que $\xi$ es un difeomorfismo con $x$, por lo que se plantea que $h(\alpha,x)=\kappa(\alpha,\xi).$ Entonces, habiendo descrito esto, se puede obtener la siguiente ecuación diferencial conformable:
$$\frac{1}{\text{Bi}_h}\frac{\partial \theta}{\partial \xi} +\theta = 0 $$
Que a su vez puede ser descrita de la siguiente manera: 
$$\frac{k}{L\kappa(\alpha,x)}\frac{\partial \theta}{\partial \xi} +\theta = 0 $$
Sea $\frac{k}{L\kappa(\alpha,\xi)}= \kappa_0(\alpha,\xi)$, entonces: 
$$\kappa_0(\alpha,x)\frac{\partial \theta}{\partial \xi} +\theta = 0 $$
La forma funcional de $\kappa_0$ es la siguiente: 
$$\kappa_0 (\alpha,x) = \frac{k}{LC\text{Re}(x)^\alpha}$$


Resolviendo la ecuación diferencial conformable: 
$$\kappa_0(\alpha,x)\frac{\partial \theta}{\partial \xi} = -\theta $$

Entonces:
$$\kappa_0(x;\alpha) \theta'(\xi) = bf(\xi)$$
Por lo tanto:
$$\frac{f'(\xi)}{f(\xi)} = -\frac{1}{\kappa_0(\xi;\alpha)}$$
Integrando esta ecuación
$$\begin{align}
\int_{\xi_0}^\xi\frac{\theta'(z)}{\theta(z)}dz & = -\int_{\xi_0}^\xi\frac{1}{\kappa_0(z;\alpha)}dz \\

\ln{\frac{\theta(\xi)}{\theta(\xi_0)}} &=  -\int_{\xi_0}^\xi\frac{LC\text{Re}(z)^\alpha}{k}dz \\

\ln{\frac{\theta(\xi)}{\theta(\xi_0)}} &=  -\frac{LC}{k}\int_{\xi_0}^\xi\text{Re}(z)^\alpha dz 
\end{align}$$

Algunas referencias: 
[Sobre las funciones de disipación](https://www.sciencedirect.com/topics/engineering/dissipation-function)
[Velocidad en la superficie de materiales](https://www.sciencedirect.com/topics/engineering/surface-velocity)
[Free stream velocity](https://www.sciencedirect.com/topics/engineering/free-stream-velocity)
[Coeficientes de película](https://www.sciencedirect.com/topics/engineering/film-coefficient)
[Capa límite](https://www.sciencedirect.com/topics/earth-and-planetary-sciences/thermal-boundary-layer)
[Otras técnicas](https://reader.elsevier.com/reader/sd/pii/S2090447920301271?token=C275AEB0A4B1340A32CC5A82B421FE478514BE1E8CAA040219F70715829596094282A410B7F984A98179970D1D082D64&originRegion=us-east-1&originCreation=20220531162942)
## Aplicación 2

Supongamos un modelo en el que busca describirse el transporte; usualmente se utiliza la ley de Fourier: 

$$\textbf{q}=k\nabla T$$

Aplicando el balance de energía de manera local: 
$$\nabla \textbf{q} = -\rho C_p\frac{\partial T}{\partial t}$$

Y surge la ecuación de conducción de calor tradicional: 
$$\frac{\partial T}{\partial t} = \alpha \nabla^2T$$

Donde $\alpha = \frac{k}{\rho C_p}$. Esta ecuación es válida suponiendo que la conductividad, densidad, y capacidad calorífica sean todos constantes en el intervalo de temperatura. Sin embargo, cuando los cambios en temperatura son elevados, o son tiempos muy cortos, la ecuación puede fallar. Por lo tanto, vale la pena considerar el caso en el que estos valores dependen de la temperatura; es decir: 

$$\frac{\partial T}{\partial t} = \nabla\left[\alpha(T) \nabla T\right]$$

Antes de considerarlo en dos o tres dimensiones, imaginemos el caso unidimensional:

$$\frac{\partial T}{\partial t} = \frac{\partial}{\partial x}\left[\alpha(T) \frac{\partial T}{\partial x}\right]$$

He encontrado que ya se ha trabajado este modelo con $\alpha(T)$, tanto por  [transformación de Boltzmann](https://www.sciencedirect.com/science/article/pii/S0364591621000122), como con modelos de [difusión anómala](https://doi.org/10.1039%2FC4CP03465A), que son análogos a derivadas conformables en el caso de subdifusión, y con derivadas fraccionales en casos de sobredifusión