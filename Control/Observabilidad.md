# Observabilidad
La observabilidad de un [[Sistema dinámico|sistema dinámico]] es una medida de qué tan bien se pueden inferir los estados de un sistema, con la información provista por las salidas externas. 

## Matriz de observabilidad
En un sistema lineal, descrito en su forma de [[Espacio estado|espacio estado]], se puede calcular la matriz de observabilidad de la siguiente manera: 
$$\mathcal{O} = \left[\matrix{C\\CA\\CA^2\\\vdots\\CA^{n-1}}\right]$$
El rango de renglón de la matriz $\mathcal{O}$ es el rango observable del espacio estado; si el rango de la matriz es igual al número de estados $n$ que tiene el sistema, entonces se dice que el sistema es observable. 
$$\mathrm{rank}(\mathcal{O}) = n\Rightarrow\mathrm{Observable}$$

Si el rango de la matriz es menor, implica que existen estados no observables, y la medida de los no observables es el [[Kernel|kernel]] de la matriz. 

La matriz de observabilidad es el dual de la matriz de [[Controlabilidad|controlabilidad]].