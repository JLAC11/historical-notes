5 / abril / 2022
10:00 am 
- Calibro el turbidímetro con agua desmineralizada (agua de plancha) y dejo esta agua en un frasco por si llega a requerirse nueva calibración en el futuro.
- Tanto en el caso de 20 NTU como 200 NTU del medidor de turbidez se ajusta para que este sea el 0.
- Se toma una medida para ver la magnitud de la turbidez esperada en los datos cuando se tomen diferentes muestras.
- Los datos pueden encontrarse [aquí](Docs_ing_ambiental/DatosAguaTratamiento.xlsx).
- Debido a que la turbidez se encuentra en el orden de 50 NTU, se usará este setting. 

11 / abril / 2022
11:20 am
- Se hace análisis con medidor de pH, conductímetro y medidor de turbidez de muestras de agua de lavado y de enjuagado. 
	- Al obtenerse el pH se encuentra que está alrededor de 6.3, y al medirse con agua simple también se encuentra en pH de alrededor de 6.3. 
	- Se levanta la sospecha de que pueda estar mal calibrado el medidor de pH. 
	- Se considera la posibilidad de hacer un buffer a pH 6.86 con el fin de calibrarlo nuevamente y quedar en una precisión de $\pm0.1$ pH. 
- Se sacan cálculos de cuánta agua debe poder pasar por el sistema. Se obtienen 2 tambos de aproximadamente 100 litros de agua al día, por lo que suponiendo que se traten en 8 horas: $$\frac{200 L}{d}\frac{1d}{8h}\frac{1h}{60 min}\frac{1000 mL}{1L} = 416.6 \frac{mL}{min}$$
- El diseño, después de discutirse con el equipo, consiste en 3 etapas:
	1. Sedimentación. Busca eliminarse una fracción de los sólidos; principalmente aquellos provenientes de fibras de tela o residuos que hayan venido en la ropa. 
	2. Electrocoagulación. Busca poder descomponerse en medida de lo posible a los detergentes y otros residuos que puedan quedar en suspensión al modificar el potencial $\zeta$ de las partículas y favorecer la coagulación. 
		- Para lograrlo, se añade $\mathrm{Al_2(SO_4)_3}$. 
		- Se planea hacer el cátodo de cobre y el ánodo de grafito, con el fin de reducir el incremento en salinidad del agua, además del sulfato de aluminio añadido en este paso.
	3. Filtrado. Tras haber eliminado la mayor parte de los sólidos, planea construirse un filtro con las siguientes [capas](https://dspace.lib.cranfield.ac.uk/bitstream/handle/1826/14299/Ncube_P_2015%20%20Final%20Thesis.%20%20Jan18.%20%20NOT%20Restricted.pdf?sequence=1&isAllowed=y):
		1. 

19:40
Se realiza una primera prueba con la idea de hacer la electrocoagulación. Tras haber electrocoagulado con la adición de sulfato de aluminio y con un cátodo de cobre y ándodo de grafito a 20 V se obtiene una reducción significativa en la turbidez del agua. se crea una espuma en la parte superior del agua, debido a la formación de burbujas de oxígeno e hidrógeno, y por la coagulación de algunas partículas. 
Se sugiere utilizar otro ánodo en vez del de grafito porque a un sobrevoltaje tan elevado no solamente se oxida formando dióxido de carbono que acidifica al agua, sino porque también llegan a desprenderse láminas del material, que aunque pueden fácilmente ser filtradas, puede resultar en un esfuerzo sobre el filtro posterior más elevado de lo deseado. 