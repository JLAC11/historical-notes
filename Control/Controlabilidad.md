# Controlabilidad

La controlabilidad es una medida en la cual un [[Sistema dinámico|sistema dinámico]] puede llegar a ser controlado por medio de una acción sobre él. Juega un rol crucial en muchos problemas de [[Control|control]], como la estabilización de sistemas inestables por medio de [[Control a lazo cerrado|control a lazo cerrado]] o [[Control óptimo|control óptimo]].

## Matriz de controlabilidad

En un [[Sistema LTI|sistema lineal invariante en el tiempo]], descrito en su forma de [[Espacio estado|espacio estado]], se puede calcular la matriz de controlabilidad de la siguiente manera: 
$$\mathcal{C} = \left[\matrix{B&AB&A^2B&\dots &A^{n-1}B}\right]$$
El rango de la matriz $\mathcal{C}$ es el rango controlable del espacio estado; si el rango de la matriz es igual al número de estados $n$ que tiene el sistema, entonces se dice que el sistema es controlable. 
$$\mathrm{rank}(\mathcal{O}) = n\Rightarrow\mathrm{Observable}$$

Si el rango de la matriz es menor, implica que existen estados no controlables, y la medida de los no controlables es el [[Kernel|kernel]] de la matriz. 

Es el dual matemático de la [[Observabilidad|matriz de observabilidad]].