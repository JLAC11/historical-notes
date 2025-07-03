# Cálculo de orden fraccional

El cálculo de orden fraccional es una técnica de cálculo que consiste en extender la idea de las [[Derivada|derivadas]] y de las [[Integral|integrales]] más allá de los números enteros, tomando la idea de convertirlos en un [[Operador|operador]], de la siguiente manera:

$$_aD_r^mf(t) = \left.\frac{d^m}{dt^m}f(t)\right._a^t$$
Donde el operador $_aD_t^m$ es el operador diferencial de orden $m$ en el tiempo comprendido entre $a$ y $r$, tradicionalmente. Sin embargo, si se permite que $m$ tenga valores no enteros, puede definirse el operador de una manera similar:

$$
_aD_r^m = 
\begin{cases}
\frac{d^m}{dt^m} &m>0,\\
1 &m=0,\\
\int_a^r(d\tau)
^{-m}&m<0\end{cases}
$$