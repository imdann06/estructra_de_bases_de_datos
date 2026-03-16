Comparación de Estructuras de Datos para Gestión de Estudiantes
Descripción del Proyecto:
Este proyecto implementa y compara el rendimiento de diferentes estructuras de datos para la gestión de un sistema con 10,000 registros de estudiantes. Cada estudiante tiene un ID nombre y promedio. El objetivo es analizar la eficiencia de búsqueda, inserción y listado en estructuras como listas lineales, Árboles  (ABB) y Árboles B+.

Funcionalidades Implementadas
El sistema permite:

Buscar un estudiante por su ID. Insertar nuevos estudiantes. Listar todos los estudiantes
Estructuras de Datos Analizadas
Lista Lineal: Una implementación básica utilizando una lista de Python.
Árbol ABB: Una estructura de árbol donde cada nodo tiene como máximo dos hijos, y los valores de los nodos hijos izquierdos son menores que el padre y los derechos son mayores.
Árbol B+: Una estructura de árbol auto-balanceada, optimizada para almacenamiento en disco, que garantiza un rendimiento de búsqueda eficiente para grandes volúmenes de datos.


Instalación
Para ejecutar este proyecto, necesitarás instalar las siguientes librerías de Python:

pip install Faker bplustree
Faker: Utilizada para generar datos de estudiantes aleatorios.
bplustree: Implementación del Árbol B+.
Uso
El proyecto se ejecuta en un entorno de Jupyter/Colab Notebook. Sigue los pasos:

Generación de Datos: Inicialmente, se generan 10,000 estudiantes con IDs, nombres y promedios aleatorios. los IDS se generan ordenados, 1 hasta 10.000
Sistema Interactivo (Lista): Se presenta un menú interactivo para interactuar con la lista lineal de estudiantes (buscar, insertar, listar).
Medición de Rendimiento: Se ejecutan pruebas de rendimiento para medir el tiempo de 1000 búsquedas aleatorias en cada estructura de datos (Lista, ABB, Árbol B+).

--------------------------------------------------------------------IMPORTANTE------------------------------------------------------------------------------------
Uso: El codigo genera 10.000 estudiantes con IDS ordenadas, asi que cuando se ejecuta una primera vez lanza los resultados de rendimiento solo para IDS ordenadas, por eso en el ultimo bloque de codigo, se encuentra la siguiente linea de codigo, random.shuffle(estudiantes) # desordena la lista de estudiantes, esto desordena la lista de estudiantes por tanto, se ejecuta nuevamente el codigo desde el segundo bloque donde se empiezan a medir los tiempos para las IDS en desorden, este codigo se debe ejecutar en Google colab debido a este diseño.
------------------------------------------------------------------------------------------------------------------------------------------------------------------

A continuación, se presenta un resumen de los tiempos de búsqueda para 1000 búsquedas aleatorias:

IDs Ordenadas
Lista Lineal: Alrededor de 0.028 segundos
ABB: Alrededor de 0.247 segundos (El ABB degenera a una lista enlazada con inserciones ordenadas).
Árbol B+: Alrededor de 0.002 segundos (Rendimiento excelente y consistente).
IDs Desordenadas
Lista Lineal: Alrededor de 0.737 segundos (El rendimiento se degrada significativamente).
ABB: Alrededor de 0.0008 segundos (El ABB se balancea mejor con inserciones aleatorias).
Árbol B+: Alrededor de 0.140 segundos (Rendimiento robusto y eficiente).
Conclusión
Los resultados demuestran claramente que las estructuras de datos basadas en árboles, especialmente el Árbol B+, ofrecen una eficiencia de búsqueda superior para grandes volúmenes de datos, superando ampliamente a las listas lineales y mostrando un mejor rendimiento que los ABB estándar cuando los datos son insertados de manera que podrían desbalancear el árbol.
