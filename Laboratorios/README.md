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

Dado que SHA-256 no es reversible, la única solucion que tenemos es:

Generar todas las posibles secuencias de 10 dígitos.
Convertir cada número a formato de 10 dígitos (con ceros a la izquierda).
Calcular su hash SHA-256.
Compararlo con el hash objetivo.
Detenerse cuando coincidan.

Problema 2:
Dado el hash raíz (Merkle root) de un árbol de Merkle y un conjunto de transacciones conocidas, el objetivo es determinar el orden de las transacciones que produce dicho root.

Objetivo

Encontrar una permutación de las transacciones tal que:

MerkleRoot(transacciones) = root_objetivo

Reglas del problema

Las transacciones son conocidas.
El orden de las transacciones afecta el resultado del árbol.
Cada transacción se convierte en un hash utilizando SHA-256.

Los nodos del árbol se combinan de dos en dos:

hash_padre = SHA256(hash_izq + hash_der)

La concatenación respeta el orden (izquierda a derecha).
Si en un nivel hay un número impar de nodos, el último nodo sube al siguiente nivel sin modificarse.
El proceso se repite hasta obtener el Merkle root.

Dado que el Merkle root depende del orden de las transacciones y no existe una forma directa de deducir dicho orden a partir del hash, la solucion planteada es:

Generar todas las permutaciones posibles de las transacciones.
Para cada permutación:
Construir el árbol de Merkle.
Calcular el root correspondiente.
Comparar el resultado con el root objetivo.
Detenerse cuando coincidan.
