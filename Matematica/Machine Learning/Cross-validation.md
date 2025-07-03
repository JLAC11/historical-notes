# Cross-validation

En [[Machine Learning|ML]], cuando no se tienen suficientes datos para hacer [[Training-Validation-Testing]] suele proponerse hacer una validación cruzada.

***NOTA:*** Cuando se hace validación cruzada, los parámetros pueden encontrarse subestimados.

## K-Fold cross-validation

Consiste en usar una parte para ajustar el modelo y puego probarla. Por ejemplo, supongamos que se divide en aproximadamente 5 pedazos del mismo tamaño:
|1|2|3|4|5|
|-|-|-|-|-|
|T|V|T|T|T|
Donde T implica entrenamiento y V validación. 
Una vez que se hace este entrenamiento y validación, se hace con otro conjunto, por ejemplo:
|1|2|3|4|5|
|-|-|-|-|-|
|T|T|V|T|T|
Con esto se compara nuevamente para ver si el modelo es adecuado. 

## LOO-CV
Se toman todos los datos menos uno y se validan de esta manera