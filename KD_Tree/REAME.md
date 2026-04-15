# KD-Tree

Este proyecto implementa un árbol KD (Bidimensional) desde cero para resolver problemas de búsqueda en un sistema de logística.

Se trabaja con coordenadas (x, y) de puntos de entrega y se busca responder eficientemente:

- ¿Qué puntos están dentro de un radio dado?
- ¿Cuál es el punto más cercano dentro de ese radio?

---

# Objetivo

Implementar y analizar un **KD-Tree** y compararlo con una solución de fuerza bruta, evaluando:

- Correctitud de resultados
- Eficiencia en tiempo
- Escalabilidad

---


# Construcción del árbol KD

El árbol se construye recursivamente:

1. Se selecciona un eje (x o y)
2. Se ordenan los puntos
3. Se toma la mediana
4. Se divide el espacio en dos

Esto garantiza un árbol balanceado.

---

# Búsqueda en radio

Se recorre el árbol:

- Se evalúa si un punto está dentro del radio
- Se decide qué ramas explorar
- Se podan regiones innecesarias

---

# Pruebas realizadas

Se validó el correcto funcionamiento mediante:

- Comparación entre KD-Tree y fuerza bruta
- Pruebas con diferentes tamaños de datos

# Análisis de rendimiento

Se realizaron experimentos con distintos tamaños:
[5, 6, 7, 8, 10, 20, 50, 100, 500, 1000, 2000, 5000, 10000]

Resultados
Se midieron:

Tiempo de del KD-Tree
Tiempo de fuerza bruta

A partir de los experimentos realizados, se observa que el árbol KD presenta un mejor desempeño en el tiempo de consulta en comparación con la búsqueda por fuerza bruta, especialmente a medida que aumenta el tamaño del conjunto de datos.
Sin embargo, el árbol KD introduce un costo adicional asociado a su construcción. En los casos donde se realiza una única consulta o el tamaño de datos es pequeño, la fuerza bruta puede ser mas rapida, A medida que el número de consultas aumenta,es mucho mejor el timpo del arbol KD que la fuerza bruta.

# Discusión de resultados

Se observa que:

- Para tamaños pequeños, la diferencia entre métodos es baja
- A medida que el número de puntos aumenta, la fuerza bruta se vuelve más costosa
- El KD-Tree mejora significativamente el tiempo de búsqueda

