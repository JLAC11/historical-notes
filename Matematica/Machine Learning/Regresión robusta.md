# Regresión robusta

Técnica de [[Machine Learning]]

$$m(X) = \mathbb{E}(Y|X)$$

[[Regresión Lineal|Mínimos cuadrados]] no es robusto basically, por su función de pérdida.

![[RobustReg]]

Entonces para mejorar la robustez, básicamente cada punto tendrá un peso en sus residuales: 

$$w=K(\hat{\epsilon})$$
Entonces, la función de pérdida puede ser:
$$\mathcal{L} = \frac{1}{\sum K(\hat{\epsilon}_i)}\sum K(\hat{\epsilon}) f(x_i)$$