# Regresión lineal

Dados unos observables (o variables [[Variable exógena|exógenas]]):
$$\mathbf{X}: x,x^2,\exp{x},...$$
Se busca predecir un conjunto de variables de salida $y$, con una ecuación de la siguiente manera:
$$y\sim\beta\mathbf{X}$$

## Regresión lineal simple

Dado un modelo de la siguiente manera:
$$\mu_{y|x} = \beta_0 + \beta_1x$$
Se buscan hallar los coeficientes $\beta_0$ y $\beta_1$ aproximen adecuadamente a los datos. En este contexto, que aproximen adecuadamente se refiere a que [[Optimización|minimice]] una [[Función de pérdida|función de pérdida]].
Una de las funciones de pérdida más comunes es la de suma de los cuadrados, definida de la siguiente manera:

$$SSR := \sum_{i=1}^n\left(y_i-E(y|x_i)\right)^2$$
#TODO 
$$\hat{\beta}_0=\bar{y}-\hat{\beta}_1\hat{x}; \hat{\beta}_1 = \frac{S_{xy}}{S_{xx}}$$
$$S_{ij}=\sum_{k=1}^i(i-\bar{i})\sum{m=1}^{j}(j-\bar{j})$$

## Regresión lineal múltiple

Ahora, no solo existe una sola variable aleatoria, sino que existen varias variables para estimar las salidas del sistema.
Sea una distribución normal multivariada:
$$\pmatrix{\mathbf{y}\\\mathbf{x}}= \mathcal{N}\left(\pmatrix{\mu_y\\\mu_x},\pmatrix{\Sigma_{yy}&\Sigma_{yx}\\\Sigma_{xy}&\Sigma_{xx}}\right)$$
Donde $\pmatrix{\mu_y\\\mu_x}$ es el vector de valores esperados, y $\pmatrix{\Sigma_{yy}&\Sigma_{yx}\\\Sigma_{xy}&\Sigma_{xx}}$ es la [[Matriz de covarianza|matriz de covarianza]]. Entonces:
$$\mathbf{y|x}\sim\mathcal{N}\left(\mu_y+\Sigma_{yx}\Sigma_{xx}^{-1}(\mathbf{x}-\mu_x),\Sigma_{yy}-\Sigma_{yx}\Sigma_{xx}^{-1}\Sigma_{xy}\right)$$
### Demostración
Considere la matriz:
$$A = \left[\matrix{I&-\Sigma_{yx}\Sigma_{xx}^{-1}\\\mathbf{0}&I}\right]$$
Sea $\mu = \left[\matrix{\mu_y\\\mu_x}\right]$ y $\Sigma = \left[\matrix{\Sigma_{yy}&\Sigma_{yx}\\\Sigma_{xy}&\Sigma_{xx}}\right]$
Entonces, $A\pmatrix{\mathbf{y}\\\mathbf{x}}\sim\mathcal{N}\left(A\mu,A\Sigma A^T\right)$. Computando estas expresiones:
$$A\pmatrix{\mathbf{y}\\\mathbf{x}} = \pmatrix{\mathbf{y}-\Sigma_{yx}\Sigma_{xx}^{-1}\mathbf{x}\\\mathbf{x}}\equiv \pmatrix{\mathbf{u}\\\mathbf{x}}$$
$$A\mu = \pmatrix{\mu_y-\Sigma_{yx}\Sigma_{xx}^{-1}\mu_x\\\mu_x}$$
Debido a que $\pmatrix{\mathbf{u}\\\mathbf{x}}$ es una variable normal y la covarianza $\mathrm{Cov}(\mathbf{u},\mathbf{x})=0$, esto implica que son independientes, por lo que tiene la misma distribución que $\mathbf{u}$, que es la siguiente: 
$$\mathbf{u}\sim\mathcal{N}\left(\mu_y-\Sigma_{yx}\Sigma_{xx}^{-1}\mu_x,\Sigma_{yy}-\Sigma_{yx}\Sigma_{xx}^{-1}\Sigma_{xy}\right)$$
#TODO 
Dado este resultado, entonces definiendo:
$$\mu_{y|x} = \mu_y+\Sigma_{yx}\Sigma_{xx}^{-1}(\mathbf{x}-\mu_x)$$
$$\Sigma_{y|x}=\Sigma_{xx}$$
> "Los datos son como los muertos, no es que te hablen, pero si eres medio brujo... maybe te dicen algo"
\- Irving Gomez, 2022

$$\mathbb{V}(x) = \mathbb{E}_x\left[(\mathbf{x-\mu_x})(\mathbf{x-\mu_x})^T\right]$$
Similarmente para la varianza en $y$
Supongamos que $\mathbf{x}\equiv x\in\mathbb{R}$ y $\mathbf{y}\equiv y\in\mathbb{R}$, y que contando con un muestreo $\mathcal{D}_n = ((x_1,y_1),...,(x_n,y_n))$ de variables aleatorias independientes e idénticamente distribuidas con la misma distribución que el vector genérico $(x,y)$. Entonces, algunos estimadores son los siguientes:
$$\hat{\Sigma}_{xx} = \frac{1}{n}\sum_i(x_i-\bar{x})^2$$
$$\hat{\Sigma}_{yy} = \frac{1}{n}\sum_i(y_i-\bar{y})^2$$
$$\hat{\Sigma}_{yx} = \frac{1}{n}\sum_i(y_i-\bar{y})(x_i-\bar{x})=S_{xy}$$
$$\hat{\mu}_{y|x}\equiv\hat{y}|x=\hat{\beta}_0 + \hat{\beta}_1x$$, donde:
$$\hat{\beta}_0 = \bar{y}-S_{yx}S_{xx}^{-1}\bar{x}$$
$$\hat{\beta}_1 = S_{yx}S_{xx}^{-1}$$
$$\hat{\Sigma}_{y|x} = S_{yx}-S_{xx}S_{xx}^{-1}S_{xy}$$

La manera de estimar la matriz de varianzas de $y$ dado $x$ es la suma de los residuales cuadrados, ajustados por el número de muestras. 

## Análisis de regresión
Sea $X\in\mathcal{X}$ en $\mathbb{R}^n$ el espacio de entrada (input space), y $Y\in\mathcal{Y}$ en $\mathbb{R}$ el espacio de salida (output space). Entonces, al hacer una regresión, se espera encontrar una función $f:\mathcal{X}\rightarrow\mathcal{Y}$ tal que $\left|f(X)-Y\right|$ sea pequeño. Sin embargo, debido a que tanto $X$ como $Y$ son variables aleatorias, no está muy bien definida esta noción. Entonces, se introduce el valor esperado, que sí puede ser estimado, y se convierte en el siguiente problema:
$$\arg \min \mathbb{E}_{X,Y}\left(f(X)-Y\right)^2$$
Donde se toma el riesgo cuadrático, o normal $L_2$.

$$\begin{aligned}
&\mathbb{E}_{x,y}\left[(f(x)-m(x))(m(x)-y)\right]\\
=&\mathbb{E}_{x}\left[\mathbb{E}_{y|x}\left[(f(x)-m(x))(m(x)-y)\right]\right]\\
=&\mathbb{E}_{x}\left[(f(x)-m(x))\mathbb{E}_{y|x}\left[(m(x)-y)\right]\right]\\
=&\mathbb{E}_{x}\left[(f(x)-m(x))\left(\mathbb{E}_{y|x}\left[m(x)\right]-\mathbb{E}_{y|x}\left[y\right]\right)\right]\\
=&\mathbb{E}_{x}\left[(f(x)-m(x))\left(\mathbb{E}_{y|x}\left[m(x)\right]-\mathbb{E}_{y|x}\left[m(x)\right]\right)\right]\\
=&0
\end{aligned}$$
Entonces:
$$\arg \min \mathbb{E}_{X,Y}\left[f(X)-Y\right]^2$$
$$\arg \min \mathbb{E}_{X,Y}\left[f(X)-m(X)\right]^2+ \arg \min \mathbb{E}_{X,Y}\left[m(X)-Y\right]^2$$
$$\arg \min \mathbb{E}_{X,Y}\left(f(X)-m(X)\right)^2$$

Para propósitos prácticos, las distribuciones de $(X,Y)$ son desconocidas, por lo que la función de regresión también es desconocida. Sin embargo, se puede tener acceso a un conjunto de entrenamiento $\mathcal{D}_n = \{(x_1,y_1),(x_2,y_2),...,(x_n,y_n)\}$, que permite hacer una función de pérdida empírica:
$$
\begin{aligned}
\mathcal{L}_n\left(f(X),Y\right) &= \frac{1}{n}\sum_{i=1}^n\left(f(x_i)-y_i\right)^2\\
&\equiv \mathbb{E}_{\mathcal{D}_n}\left[f(X)-Y\right]^2
\end{aligned}
$$
Entonces esta función de pérdida se puede definir de la siguiente manera:
$$\arg \min_{f:\mathcal{X\rightarrow Y}} \mathcal{L}_n\left(f(X),Y\right) = \arg \min_{f:\mathcal{X\rightarrow Y}} \frac{1}{n}\sum_{i=1}^n\left(f(x_i)-y_i\right)^2$$
Sin embargo, debe notarse que si se intenta minimizar esta expresión sobre todas las funciones $f:\mathcal{X\rightarrow Y}$ no está bien definida, ya que cualquier función que tome el valor $Y_i$ para cada valor $X_i$ tendría un riesgo de cero, por lo que existe una infinidad de soluciones. Un ejemplo muy burdo es el siguiente:
$$f(X) = \begin{cases}
Y_i, & X = X_i \\
0, & e.o.c.
\end{cases}
$$
Este tiene error 0 pero no tiene ningún poder predictivo. Por lo tanto, se modifica  a la siguiente función a minimizar:
$$\arg \min_{f\in{F_\Theta}:\mathcal{X\rightarrow Y}} \frac{1}{n}\sum_{i=1}^n\left(f(x_i)-y_i\right)^2$$
Donde $F_\Theta$ es el conjunto de funciones factibles que tenga parámetros $\Theta$. Debido a que es meramente una búsqueda de parámetros, puede obtenerse el siguiente subproblema:

$$\hat{\Theta} = \arg \min_{\Theta} \frac{1}{n}\sum_{i=1}^n\left(f_\Theta(x_i)-y_i\right)^2$$

Por ejemplo, sea $\mathcal{F}_\Theta = \left\{f:\mathcal{X\rightarrow Y}:f(X) = X^T\beta ,\beta:\left\{\beta:\beta \in \mathbb{R}^p\right\}\right\}$
Sea $\mathbf{X}=\left[\matrix{X_1^T\\\vdots\\ X_n^T}\right]$ y $\mathbf{Y}=\left[\matrix{Y_1\\\vdots\\ Y_n}\right]$, entonces, la suma:
$$\sum_{i=1}^n\left[X_i^T\beta - Y_i\right]^2$$
Puede ser escrita de la siguiente manera:
$$
\begin{aligned}
\sum_{i=1}^n\left[X_i^T\beta - Y_i\right]^2 &= \\
&= \\
&= \beta^TX^TX\beta - 2\beta^TX^TY+Y^TY
\end{aligned}
$$
Minimizando los parámetros (tomando la derivada de los parámetros $\beta$) se obtienen las ecuaciones normales:
$$2X^TX\hat{\beta}-2X^TY = 0 \iff X^T(Y-X\hat{\beta}) = 0$$
Puede demostrarse fácilmente entonces que $\hat{\beta} = (X^TX)^{-1}X^TY$
***IMPORTANTE:*** no se toma $\hat{\beta}=X^{-1}Y$ porque nada asegura que $X$ sea una matriz invertible.

### Demostración con álgebra lineal
Sea $\mathbf{X}=\mathrm{[X^{(1)},...,X^{(n)}]}, \mathbf{X}\in\mathbb{R}^{n\times p},W = \mathrm{Col}(\mathbf{X})$ y $\mathbf{Y}\in\mathbb{R}^n$


$$\mathcal{Z}\{x[n]\}=X(z) = \sum_{i=-\infty}^\infty x[n]z^{-n}$$