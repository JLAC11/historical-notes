# Inventarios
## Resumen ejecutivo
### Costos
- Capitales
- De facilidades
- De labor humana
- Financieros
- De management
- Procurement 
- Turnover: cuántos inventarios/año? 
- Precisión en stock (>98%)
- Pillage and Ullage
- Niveles de servicio (muy rígido puede ser caro)

> Know thy customer's service levels

Clases de servicios
- Críticos
- No críticos
- De entrega programada
	- Productos de tecnología p.ej.
	- Muebles

### Estrategias para manejo
- Vendor managed inventory: Vendedores manejan inventario, no los productores.
- Postponement logistics: Posponer la creación de bienes hasta que se haga el producto final en el lugar que se necesita.
- 

## Tipos de costos
- Costo operativo: $C_o$
	- ¿Cuánto me cuesta colocar un pedido?
	- Se obtiene dividiendo el sueldo del comprador entre el número de pedidos procesados por compras en un periodo determinado
	- Costo de preparar la planta para producir un pedido: implica el sueldo de los trabajadores que aseguran que hay MP suficiente, el del programador de producción que programa el pedido, el de mantenimiento si hay que lavar o preparar reactores para producir, el agua o solvente usado en el lavado del reactor,  la energía usada en la limpieza de equipos, etc. 
- Costo de almacén: $C_c$ o $C_h$ (holding cost)
	- Costos fijos de tener el almacén.
	- OJO: no es costo de inventario si es mío; si pago para almacenar entonces sí. 
- Costos financieros:
	- Costos de interés si pago aplazado
	- Costo de oportunidad (en CETES, Crypto, etc. )
	- Se consideran con precio unitario de lo que se adquiere
- Costo de merma o robo: porcentaje anual histórico de mermas o robos
- Costo de transporte de material (FOB planta por ejemplo).

![[Qmodel]]

## Modelo EOQ
![[EOC]]
Punto de reorden: Punto en el que debo hacer el pedido para que se coloque la orden y entreguen justo cuando el inventario llegue a 0. 
Las pendientes descendientes en el tiempo son la demanda, y el inventario promedio es de $\frac{Q}{2}$. Para calcular el punto de reorden, solo debe considerarse el tiempo de entrega, y con la demanda calcular el punto de reorden. 

Entonces, para poder describir este modelo: 
- $C_0$: Costo de colocar un pedido
- $C_C$: Costo anual de almacén por unidad
- $D$: Demanda anual
- $Q$: Cantidad pedida
![[Pasted image 20220401082654.png]]

