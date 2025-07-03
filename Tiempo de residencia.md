El tiempo de residencia de un reactor es definido como el tiempo que permanece un reactivo en el dispositivo antes de salir. Se toma el valor promedio pues es el más representativo; sin embargo, los tiempos de residencia pueden ser muy variables. Esto se debe a que el mezclado no es perfecto, existen fenómenos de transporte que hacen que no se transporte todo el fluido a la misma velocidad, y provoca que exista una distribución de tiempos de residencia.   

## Distribución de los tiempos de residencia

Es necesario hacer este tipo de experimentos debido a que existe una gran diferencia entre un proceso idealizado contra los procesos no ideales (reales)
1. Caracterización de reacciones no ideales
2. Determinación de problemas que puedan haber problemas

### Métodos de determinación
#### Experimento de impulso
Se inyecta una sustancia rápidamente, y se mide la concentración a la salida, formando una curva (tal cual una distribución). Se intoduce una cantidad $N_0$ y se mide a la salida; de manera numérica:
$$\Delta N = C(t)v\Delta t$$
Si el tiempo es relativamente pequeño, entonces cuando $\Delta t\rightarrow0$:
$$\frac{dN}{dt} = E(t) = \frac{v}{N_0}C(t)$$
Se conoce a $E(t)$ como función de la distribución de tiempos de residencia. Si se desconoce la cantidad inyectada, puede calcularse por medio de la integral:
$$N_0 = \int_0^\infty vC(t) dt$$
Entonces puede sustituirse en la ecuación de la siguiente manera:
$$E(t) = \frac{vC(t)}{\int_0^\infty vC(t) dt}$$

#### Experimento de escalón
Se inyecta una sustancia y se mantiene un flujo constante, y se mide concentración a la salida, formando una distribución acumulada.

Tiene varias desventajas, como:
- Es difícil mantener constante la alimentación
- Existen errores considerables por la medición de datos
- Ocupa mucho trazador

