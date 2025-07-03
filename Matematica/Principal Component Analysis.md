# PCA

Si $A$ es una matriz simétrica, es decir: 
$$A = A^T$$
Entonces se puede factorizar de la siguiente manera:
$$A = Q\Lambda Q^T$$
Que es meramente la descomposición espectral, donde $\Lambda$ es diagonal, con los eigenvalores de $A$, y $Q$ es ortogonal, con los eigenvectores de $A$.
Si $B$ es una matriz positiva definida, entonces:
$$B = VDV^T$$
$$B = VD^\frac{1}{2}D^\frac{1}{2}V^T$$

$$B = VD^\frac{1}{2}V^TVD^\frac{1}{2}V^T$$
$$B = \left(VD^\frac{1}{2}V^T\right)^2$$

#### Problemática
Queremos maximizar una matriz simétrica con su forma cuadrática en la esfera unitaria; es decir: 
$$\max_{x\in||x||^2=1}x^TAx$$

Dada una matriz simétrica $A$ el coeficiente de Rayleigh es dado por: 
$$\frac{x^TAx}{x^Tx}$$
Y el coeficiente generalizado de Rayleigh, dada una matriz simétrica $A$, y una matriz positiva definida $B$:
$$\frac{x^TAx}{x^TBx}$$

Debido a que la norma de $x$ es 1, es equivalente el problema de maximización a encontrar el máximo del coeficiente de Rayleigh.
Entonces, considerando el coeficiente de Rayleigh: 
$$x^TAx = x^TQ\Lambda Q^Tx$$
$$x^TAx = y^T\Lambda y$$
Donde $y=Q^Tx$, entonces el problema de optimización es equivalente a maximizar $y$ sobre la matriz de los eigenvalores de $A$.
Entonces: 
$$y^T\Lambda y = \sum_{i}\lambda_iy_i^2$$
Debido a que la norma de $y$ es 1, entonces: 
$$y^T\Lambda y \le \lambda_{max}\sum_iy_i^2$$
$$y^T\Lambda y \le \lambda_{max}$$
Por lo tanto el máximo es $\lambda_{max}$, es decir, el eigenvalor más grande. 


De igual forma, para el coeficiente generalizado de Rayleigh: 
$$\frac{x^TAx}{x^TBx}$$
Sea $y=B^\frac{1}{2}x$, entonces:
$$\frac{x^TAx}{x^TBx}= \frac{y^TB^{-\frac{1}{2}}AB^{-\frac{1}{2}}y}{y^Ty}$$
Entonces $y^*$ es el eigenvector más grande de $B^{-\frac{1}{2}}AB^{-\frac{1}{2}}$, y $x^* = B^{-\frac{1}{2}}y^*$
![[Pasted image 20220504204657.png]]