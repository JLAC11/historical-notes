# Potencial químico
El potencial químico de la especie $i$ se denota por $\mu_i$, y está definido como el cambio de cualquiera de las cuatro [[Ecuaciones fundamentales de la termodinámica|ecuaciones fundamentales de la termodinámica]], de la siguiente manera: 

$$\mu_i = \left(\frac{\partial F}{\partial N_i}\right)_{A,B,N_{j\neq i}}$$

Donde $F$ es alguna de las ecuaciones fundamentales, y $A,B$ son sus parámetros. Por ejemplo, para la [[Energía de Gibbs|energía de Gibbs]]: 

$$\mu_i = \left(\frac{\partial G}{\partial N_i}\right)_{T,P,N_{j\neq i}}$$

O para la [[Energía de Helmholtz|energía de Helmholtz]]:

$$\mu_i = \left(\frac{\partial A}{\partial N_i}\right)_{T,V,N_{j\neq i}}$$

Este resultado se obtiene de aplicar la [[Transformada de Legendre|transformada de Legendre]] de cualquiera de los potenciales termodinámicos.

## Soluciones ideales vs. no ideales

En la termodinámica de soluciones, es común ver el potencial químico como la suma del potencial ideal y un [[Propiedad en exceso|potencial en exceso]], de la siguiente manera:
$$\mu_i = \mu_i^I+\mu_i^E$$

Asumiendo que el potencial químico solamente dependa de la fracción molar, entonces, se obtiene la siguiente ecuación:
$$\mu_i = \mu_{i0}(T,P)+RT\ln(x_i\gamma_i)$$
Donde $x_i$ es la fracción molar del componente $i$ en el líquido y $\gamma_i$ es el [[Coeficiente de actividad|coeficiente de actividad]] de la sustancia $i$.

--------
#Termodinámica 