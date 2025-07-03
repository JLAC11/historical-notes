# Training-Validation-Testing

En [[Machine Learning|ML]] se suele usar este procedimiento cuando existen muchos datos. 

Se divide en tres fases:

## Training

Se toma un conjunto de datos para entrenar y se entrenan $M$ modelos para poder compararlos. 

## Validation

Se mide el error del modelo, pero usando el conjunto de datos de validación. Se mide el [[Error cuadrático medio|MSE]] de cada uno de los modelos y se toma el que muestre el menor error [^1]

[^1]: Alternativamente, el que muestre el menor valor de función de pérdida.
Se elige el modelo en este paso. Posteriormente, se estiman los parámetros con la unión de datos de entrenamiento y de validación.

## Testing

Para evaluar si el modelo elegido es adecuado, entonces se prueba el modelo con los datos de prueba, 