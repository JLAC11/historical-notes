# Notas generales de Mermaid

## Grafo 
### Dirigido
Se usan flechas -->
```mermaid
	graph TD;
		A<-->B-->C-->D-->A-->A;
		click A callback "Hola"
		A[Hola, soy el nuevo xd]
		B(Nuevo yo xd con bordes redondos)
		C[/Hola soy un paralelogramo/]
		D{Y Yo un rombo}
		
```
Existen varios tipos de flechas:

```mermaid
	sequenceDiagram
		participant Alice
		participant Bob
		Alice ->> John: Hello John, how are you?
		loop Healthcheck:
			John->>John:  Kay
		end
		Note left of John: Oops
		John -->> Alice: Not much bro, hbu?
		John ->> Bob: Sup?
		Bob -->> John: Not much;
		John -->> John: WHAT

```

### No dirigido
```mermaid
	graph LR %% LR: Left to right; TD: Top to bottom
		A<-->B--oA; %% Otro tipo de flechas
		A---D; %% No se pone la cabeza, sino guiones
		C-->D-->C;
		D-.->A %% Punteada
		E-->F-->E;
		C-->F-->C;
		E==>B-->E; %% Gruesa
```

## Diagrama UML

```mermaid 
classDiagram

class Box {
	- str Name
	- str[] Contents
	+ addContents()
	+ removeContents()
}

class PencilBox {
	- int size
	- char[] color
	+ getColor() Color
}

class Color {
	<<Enumeracion>>
	Rojo
	Verde
	Amarillo
	Blanco
	Azul
	Negro
}
%% A <|-- B Indica que B hereda de A
Box<|--PencilBox
%% A ..> B Indica que A depende de B
PencilBox..>Color

```