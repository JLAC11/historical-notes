# Maximizar la utilidad en una planta química

Pasos: 
1. Mapping the whole plant in monetary terms: Checar cuánto produce la planta en términos de $/h.
	- Resultado Operativo = $ generado por ventas - costos variables - costos fijos
	- NO se llega a EBIT o EBITDA
	- Error básico: NO gastar en perder empleados a menos que sea necesario. NO se dejen
	- NOTA: Pedir datos e costos de años pasados
	- Benchmarking: se comparan ustedes con industrias similatres. 
		- BASF: compara con muchos de la misma compañía
		- Compara consumo unitario (mt/mt Producto) y costo unitario ($/mt Producto)
2. Assessment of current plant condition
	- Evaluar cómo trabajan equipos dde la planta
		- Columnas
		- Reactores
		- Secadores
		- Columnas de destilación
	- Examinar limitaciones de equipos (en volumen, presión, temperatura, etc.)
	- Limitaciones por personal
	- CUELLOS DE BOTELLA
3. Assessment of base control layer of plant
	- PLC : Process Logic Control
		Técnica de control para que se sepa qué hacer de acuerdo a unas reglas lógicas. 
		Alarma si no hay el flujo solicitado, por ejemplo. 
	- Distributed Control System
		Sistema para controlar la planta de manera distribuida 
			- Estilo maestro-esclavo
			- Estilo controlador maestro y varios esclavos (no necesariamente una sola función de transferencia)
4. Assessment of loss from plant
	- Pérdidads de energía y producto
	- Aguas residuales, quemadores de gas...
	- De energía térmica
	- Analizar retorno de inversión para solucionar estos problemas.
5. Identification of improvement opportunity in plant and functional design
	- Aspectos relevantes del proceso y resultados financieros
	- Ver diagramas de flujo y P&ID 
	- Revisar históricos
	- Modelar los cambios
6. Develop advance process monitoring framework by applying latest data analytics tools
	- Medir efectividad contra una referencia adecuada
	- Proponer KPIs para una mejora continua
7. Develop real time fault diagnosis system
	- Falla de equipo puede resultar en varios días de pérdidas de producción
	- Monitorear contantemente variables como temperatura, vibración, presión, etc. 
8. Perform a maximum capacity test run
	- Incrementar 5 0 10% a veces se puede con inversiones mínimas
	- Reevisar máximo SIN PONER EN RIESGO seguridad
	- Permite identificar la forma de operar la planta con seguridad obteniendo la mayor producción 
9. Develop APC (Advanced Process Control)
	- Control MIMO
	- Control con PLC funciona bien para acoplar 1 con 1 
	- Calcuar secuencia óptima de acciones
10. Develop model based on data to operate critical equipment
	- Modelos matemáticos
	- Modelos en Aspen
11. Modelos probar
12. Siguientes pasos
	- Checar cinética
	- Checar columnas y reactores
Finalmente:
- Aplicar tecnolog{ias de diseño en los equopos de planta
- Se diseña con funcionalidad y no es común tomar el costo de operación como una estrategia de diseño
- ASPEN, HYSIS, PROII

Preguntas a formular: 
1. What are the constraints in the plant which prevent maximization of profits? 
2. What are the process parameters?
3. Are there any raw material or utility limitations? 
4. Capacity limitation in majort equipment? 
5. How will catalyst performance be impacted with increase in capacity?
6. Safety limits?
7. Process limitations?
8. Quality specs? In jeopardy?
9. Process instrument limitations like valve openings? 


Arregla tu CCM (Cuarto de Control y Motores)