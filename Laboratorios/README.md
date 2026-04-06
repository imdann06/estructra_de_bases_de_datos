Problema 1:

Dado un hash generado con el algoritmo SHA-256, el objetivo es determinar la secuencia de 10 dígitos (cada uno entre 0 y 9) que produce dicho hash.

Objetivo

Encontrar una cadena de 10 dígitos tal que:

SHA256(secuencia)=hash_objetivo

Reglas del problema
La secuencia está formada por 10 dígitos.
Cada dígito está en el rango 0–9.
La secuencia se trata como texto (string), no como número.
Se utiliza el algoritmo SHA-256.
No existe una forma directa de invertir el hash.

Dado que SHA-256 es una función criptográfica no reversible, la única estrategia general es:

Generar todas las posibles secuencias de 10 dígitos.
Convertir cada número a formato de 10 dígitos (con ceros a la izquierda).
Calcular su hash SHA-256.
Compararlo con el hash objetivo.
Detenerse cuando coincidan.

Problema 2:

