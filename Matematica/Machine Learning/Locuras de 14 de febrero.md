Teorema de Slutsky 
Convergencia débil y fuerte

sqrt(n) muhat-mu / sigma hat tiende a ser una normal (0,1)

Media: robusta ante outliers, no ante cambios en centralidad


Teorema del límite central

Si tomas dos normales independientes y las restas, sigue siendo una normal. 

$$\hat{x}_0 = \bar{x} \dot{\sim}\mathcal{N}(\mu,\sigma^2/n)$$

Entonces:
$$\hat{x}_0 - x_0 \dot{\sim}\mathcal{N}(0,\sigma^2 + \sigma^2/n)$$
$$\frac{1}{\sqrt{\sigma^2+\sigma^2/n}}(\hat{x}_0 - x_0 ) \dot{\sim}\mathcal{N}(0,1)$$
$$\frac{1}{\sigma\sqrt{1+1/n}}(\hat{x}_0 - x_0) \dot{\sim}\mathcal{N}(0,1)$$

Sabiendo que si $H \sim\mathcal{N}(\mu,\tau^2)$ entonces $$\frac{H-\mu}{\sigma}\sim\mathcal{N}(0,1)$$
Entonces, usando el teorema de Slutsky:
$$\frac{1}{\sqrt{1+\frac{1}{n}}}\frac{\hat{x}_0-x_0}{\hat{\sigma}}\sim\mathcal{N}(0,1)$$
Entonces se puede estimar que el valor de un $x$ dados los estimadores de su población puede definirse en términos de una confianza $\alpha$ de la siguiente manera:

$$x = \mathrm{P}(\bar{x}-q_{1-\alpha/2}\hat{\sigma}\sqrt{1+\frac{1}{n}}\le x\le \bar{x}+q_{1-\alpha/2}\hat{\sigma}\sqrt{1+\frac{1}{n}}$$
Donde $q_i$ representa el cuantil evaluado en $i$
