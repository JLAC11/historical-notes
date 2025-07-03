# Función de transferencia

Sea un [[Sistema LTI|sistema lineal invariante en el tiempo]] con entradas $X(t)$ y salidas $Y(t)$, entonces, su función de transferencia es definida de la siguiente manera: 

$$H(s) = \frac{Y(s)}{X(s)}$$
Donde $H(s)$ es la función de transferencia, y $Y(s)$ y $X(s)$ son las [[Transformada de Laplace|transformadas de Laplace]] de las salidas y las entradas, respectivamente.

Para una representación de un [[Espacio estado|espacio estado]] de un sistema [[Sistema LTI|lineal invariante en el tiempo]]:
$$\mathbf{H}(s)=C\left(Is-A\right)^{-1}B+D$$

$$\dot{x} = Ax$$
Anotando la transformada de Laplace: 
$$sX(s) = AX(s)$$
Resolviendo la ecuación:
$$sX(s)-AX(s) = 0$$
$$\left(sI-A\right)X(s)=0$$
Puede observarse que la solución de esta ecuación es equivalente a encontrar los [[Eigenvalores|eigenvalores]] de la matriz $A$. Estos a su vez representan los [[Polos|polos]] de la función de transferencia.