# Sistemas de recomendación

> Sistemas de recomendación
- Adal Acuña y Jero de la Mora

## ¿Qué es?

Es un algoritmo que genera predicciones de gustos e intereses de usuarios o consumidores en base a información sobre sus preferencias.
- Suele basarse en ratings o likes.
- Busca hacer una lista personalizada de recomendaciones pra un usuario.
- Se usan por gran diversidad de productos o información ofrecidos
- Usuarios con preferencias distintas

## Tipos
### Content based
- Recomienda productos similares a los que el usuario ha consumido. 
- Compara productos con base en sus atributos.
- Atributos:
	- Palabras clave
	- Características
	- Apariencia
	- Clasificación hecha por humanos (necesariamente por humanos?)

```mermaid
graph LR;
A(Fuente de información)--->B(Procesamiento de información)
B-- Pr

```

![[Pasted image 20220404201100.png]]

En el procesamiento de la información: 
- Se extraen atributos o propiedades del producto
- Modelo de espacio vectorial 
- Palabras clave en una estructura ordenada
$$d_j = \{w_{1j},...,w_{kj}\}$$
$$w_{kj} = TF_{ij}\cdot IDF_k$$

$$TF-IDF(t_k,d_j) = TF(t_k,d_j)\cdot\log\frac{N}{n_k}$$
- $f_{kj}$ Frecuencia con la que ocurre la palabra $k$ en el documento $j$
- $N$: Número de documentos
- $n_k$: número de documentos dodne la palabra $k$ aparece por lo menos una vez
$$TF(t_k,d_j) = \frac{f_{kj}}{\max_z f_{zj}}$$

- Coseno de similitud: 
$$sim(d_i,d_j) = \frac{}{}$$
![[Pasted image 20220404201627.png]]
Entre más palabras en común tengan, mayor es esta similitud de coseno

#### Algoritmo de Rocchio
![[Pasted image 20220404201655.png]]
### Collaborative filtering

Se analiza a los usuarios, en vez de a los productos. 
Se asemeja a una recomendación en la vida real.
- Principio social
	- Recomendación: sugerencia de amigos, conocidos, grupos similares, etc.
	- Correlación persona-persona
		- Evalúa similitud
		- Crea grupos según las evaluaciones que tienen las personas
- Premio Netflix: competencia organizada para mejorar su sistema de recomendación
	- Parteaguas en comunidad de datascience/ML
	- Bases de datos industriales
	- Nuevas técnicas de recomendación
	- Desarrollo de nuevos algoritmos

#### Factorización Funk MF
Propone una factorización de la siguiente manera: 
$$R = KW^T$$
- $R\in\mathbb{R}^{\text{users}\times \text{items}}$
- $H\in\mathbb{R}^{\text{users}\times \text{latent factors}}$
- $W^T\in\mathbb{R}^{\text{latent factors}\times \text{items}}$
- Permite relacionar objetos en lugar de personas
- Permite el uso de [[Error cuadrático medio|MSE]] y MAE para evaluar desempeño
- Predice los ratings de cada elemento según el usuario
- "Explica" la razón de la recomendación.

#### Sistemas de recomendación por recomendación social

$$RS(u,i) = \exp(-\alpha t(i))\sum_{v\in N^T(u)}S^T[u,v]\sum_{r\in R(v,i)}R[v,i]$$

### Otros tipos
- Sistemas híbridos: mezclan colaborativos con basados en contenido
	- Recomendaciones más personalizados y más variados a la vez
- Sistemas de recomendación neuronales
	- Integran redes neuronales en el proceso.
- No personalizados: concursos de popularidad
- Usuario genérico/promedio
	- Problemas: recomendaciones no personalizadas; "loop" de popularidad: lo no popular nunca se recomienda; lo popular se vuelve más popular.
- Location based
	- Consecuencia del uso de teléfonos móviles 
	- Servicios de localización geográfica
	- Usan otras variables para hacer recomendaciones
		- Variables tradicionales
		- Variables de localización
			- Ubicación actual
			- Historial de ubicaciones
- Knowledge based
	- Se basan en conocimiento del usuario
		- Demografía
		- Edad
		- Ocupación
		- Etc.
	- Requiere enormes bases de datos
	- Preocupaciones de privacidad
	- Usos notables
		- Ads
			- Facebook
			- Google
			- Amazon
		- Online dating
			- Tinder
			- Bumble
			- Sitios de citas
## Principios generales en los sistemas de recomendación
- Model based
	- Se genera un modelo más allá de las similitudes
	- Usados cuando se tiene información incompleta
		- SVD
		- Redes bayesianas
- Memory based
	- Recae en una gran base de datos con elementos
		- Busca similitudes entre objetos o usuarios
		- Medidas sencillas
			- Número total de similitudes
			- Correlación de Pearson
- Aprendizaje no supervisado
	- Se generan clusters basically
- Aprendizaje supervisado
	- Se cuentan con grupos de elementos y/o usuarios similares
	- Se genera basada en usuarios con gustos similares o en elementos que tengan características similares a los que le agraden al usuario
- Evaluación: 
	- Evaluación experimental
	- A/B testing 
- Problemas
	- Cold start: ¿si tienes un nuevo usuario o un nuevo producto?
	- Computacionales: cantidad de datos gigantescos
		- Usuarios: muchísimos usuarios
		- Objetos/productos: cantidades enormes de artículos que deben además catalogarse todo el tiempo.
		- Velocidad de búsqueda: debe ser rápido
		- Velocidad vs precisión.
	- No entienden normas sociales
		- Usuarios menores de edad
	- Cámaras de eco
		- Publicaciones afines a la visión del usuario
	- Privacidad
		- Más información = más precisión
		- Aversión a que las compañías sepan sobre usuarios
		- El sistema sabe más de ti que lo que sabes de ti mismo a veces

## Preguntas
- ¿Por qué conviene tener personalizadas? ¿Difieren mucho de las "top" elegidas?
- ¿Qué tan ético es promover el consumo con ellos?
- Principio social: ¿por qué usar un sistema colaborativo y no meramente una clasificación? O ¿qué algoritmos pueden haber? 
- ¿Qué eran los factores latentes? ¿Cómo los determinas?

### Calificación 
- Tecnicidad: 
- Claridad: 
- Comentarios adicionales: 
