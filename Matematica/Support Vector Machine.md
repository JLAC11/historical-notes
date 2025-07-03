# SVM
- Algoritmo de [[Machine Learning]]
- Algoritmo de clasificación binaria que puede adaptarse a un problema de clasificación multicplase
- Modelo de aprendizaje automático utilizado en aplicaciones de espectro amplio de áreas de estudio
### Problemática
¿Cuál es el mejor hiperplano que pueda separar a los datos?
¿Cuáles hiperplanos deben considerarse?

## Máquina de Soporte Vectorial Lineal
$$w^Tx+b = 0$$
- $w$ representa un vector al hiperplano.
- $\frac{b}{||w||}$ la distancia perpendicular del hiperplano origen.

### ¿Cómo determinarlo? 
$w^Tx+b \ge 1$  para $y_i=1$
$w^Tx+b \le -1$  para $y_i=-1$
Entonces los hiperplanos $H_1$ y $H_2$ son justamente dados por estas desigualdades al multiplicarse por $y_i$.
![[Pasted image 20220404211710.png]]
### Longitud del margen: 
Al proponer un $h_j$ que resida en el hiperplano $w^Tx+b = -1$ se calcula la distancia perpendicular desde $x_j$ hacia el otro mediante una variable $z$ que esté en términos de $w$.
![[Pasted image 20220404211832.png]]

Busca maximizarse esta distancia entre los hiperplanos $H_1$ y $H_2$ para que la clasificación sea la más clara, que debido a que 
$$z = \frac{2}{||w||}$$ entonces puede plantearse un problema de minimización: 
$$\min ||w||$$
Sujeto a:
$$y_i(w^Tx_i+b)\ge1$$
Sin embargo al minimizar $$||w||$$ se ve que no es diferenciable en 0 por lo que se usa $$\frac{||w||^2}{2}$$
![[Pasted image 20220404212040.png]]

Si se resuelve el problema dual entonces luce de la siguiente manera: 
![[Pasted image 20220404212239.png]]

Que es meramente un problema de optimización cuadrático convexo. 
## Máquina de Soporte Vectorial y el margen suave

Se maximiza el margen, y en el caso lineal se pueden construir márgenes duros, los cuales no consideran errores al momento de clasificar, por lo que si se introduce el concepto de margen suave, se puede introducir una variable de holgura positiva, donde los datos no son perfectamente separables: 
$w^Tx+b \ge 1$  para $y_i=1-\xi_i$
$w^Tx+b \le -1+xi_i$  para $y_i=-1$
$$\xi_i\ge0\forall i$$
Donde $\xi_i,i=1,...,L$.
Ajustando con esta idea: 
![[Pasted image 20220404212834.png]]

***Nota de sospecha:*** Será meramente una regularización? 
## Máquina de Soporte Vectorial para casos no lineales

Kernel trick: consiste en hacer una función llamada kernel que permita separarlas 
- Lineal
- Polinomial
- Base radial
![[Pasted image 20220404213504.png]]
## Máquina de Soporte Vectorial para multiclase
- Enfoques 
	- Uno contra todos ![[Pasted image 20220404213821.png]]
	- Uno contra uno ![[Pasted image 20220404213914.png]]

[[Matriz de confusión]]

yao es muy relajada
super proximal
aro la presionaba y marcaba - tsb 



