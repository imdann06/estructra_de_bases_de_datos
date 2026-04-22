# QuadTree

Este proyecto implementa un árbol **QuadTree bidimensional** desde cero para resolver problemas de búsqueda en un sistema de logística.

Se trabaja con coordenadas (x, y) de puntos de entrega y se busca responder eficientemente:

- ¿Qué puntos están dentro de un radio dado?
- ¿Cuál es el punto más cercano dentro de ese radio?

## Objetivo

Implementar y analizar un **QuadTree** y compararlo con una solución de **fuerza bruta**, evaluando:

- Correctitud de resultados
- Eficiencia en tiempo


## Construcción del árbol QuadTree

El árbol se construye recursivamente:

- Cada nodo representa una región rectangular del espacio
- Se calcula el punto medio en x y en y
- El espacio se divide en cuatro cuadrantes:
  - arriba izquierda
  - arriba derecha
  - abajo izquierda
  - abajo derecha
- Los puntos se distribuyen según el cuadrante al que pertenecen
- El proceso se repite recursivamente hasta llegar a hojas

Esto permite organizar los puntos de acuerdo con su posición espacial.

## Búsqueda en radio

Para encontrar los puntos dentro de un radio dado:

- Se recorre el árbol desde la raíz
- Se calcula la distancia mínima entre el punto de consulta y la región de cada nodo
- Si una región está más lejos que el radio, se poda y no se sigue explorando
- Si no, se revisan los puntos almacenados y se continúa con los hijos

De esta manera se evita revisar regiones innecesarias del espacio.

## Pruebas realizadas

Se validó el correcto funcionamiento mediante:

- Comparación entre QuadTree y fuerza bruta
- Pruebas con diferentes tamaños de datos
- Análisis de rendimiento
- Verificación visual de los puntos dentro del radio
- Verificación visual del vecino más cercano

## Análisis de rendimiento

Se realizaron experimentos con distintos tamaños de datos:

[ 10,20,40, 50, 60, 80, 100, 200]

En cada caso se midieron:

- Tiempo de construcción del QuadTree
- Tiempo promedio de consulta con QuadTree
- Tiempo promedio de consulta con fuerza bruta

## Resultados

A partir de los experimentos realizados, se observa que el **QuadTree** presenta un mejor desempeño en el tiempo de consulta en comparación con la búsqueda por fuerza bruta, especialmente a medida que aumenta el tamaño del conjunto de datos.

Sin embargo, el QuadTree introduce un costo adicional asociado a su construcción. En los casos donde se realiza una única consulta o el tamaño de datos es pequeño, la fuerza bruta puede ser más rápida.

A medida que el número de consultas aumenta, el tiempo del QuadTree resulta más conveniente que el de la fuerza bruta.

## Discusión de resultados

Se observa que:

- Para tamaños pequeños, la diferencia entre métodos es baja
- A medida que el número de puntos aumenta, la fuerza bruta se vuelve más costosa
- El QuadTree mejora el tiempo de búsqueda gracias a la poda espacial
- La construcción del árbol tiene un costo inicial, pero se compensa cuando se realizan múltiples consultas

## Conclusión

El QuadTree es una estructura adecuada para consultas espaciales en dos dimensiones. Permite organizar los puntos por regiones y reducir el número de comparaciones en búsquedas por radio.

Aunque la fuerza bruta puede ser suficiente para conjuntos pequeños o pocas consultas, el QuadTree ofrece una mejor alternativa cuando el volumen de datos crece o cuando se necesitan muchas búsquedas.
