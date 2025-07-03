```mermaid
classDiagram

class SHYPA

class Producción

class Proyectos

class Calidad

class Logística

SHYPA<|--|>Producción
SHYPA<|--|>Proyectos
Calidad<|--|>SHYPA
Logística <|--|> SHYPA
```

```mermaid
classDiagram

class Operaciones

class Ventas

class Finanzas

class Compras

class RecursosHumanos

Operaciones<|--|>Ventas
Operaciones<|--|>Finanzas
Compras<|--|>Operaciones
RecursosHumanos <|--|> Operaciones
```
