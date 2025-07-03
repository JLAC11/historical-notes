# Controlador PID

Un controlador PID es un tipo de [[Control|controlador]] que tiene una parte proporcional, una integral y una derivativa. Se puede describir de la siguiente manera:

$$PID = K_ce(t) + K_I\int_{t_0}^te(t)\mathrm{dt}+K_D\frac{d}{dt}e(t)$$

Cuando se realiza la [[Transformada de Laplace|transformada de Laplace]], se obtiene la siguiente forma: 
$$PID(s) = K_C + \frac{K_I}{s}+K_Ds$$

Es particularmente útil cuando se intenta hacer [[Control a lazo cerrado]]. Se espera que pueda ser relativamente [[Robustez|robusto]], pues no necesariamente se conoce con certeza el sistema que se desea controlar. 