**Libro de Texto: Algoritmos y Estructuras de Datos**

**Autor: José Alejandro Jiménez Rosa**

---

```markdown
# Capítulo 1: Introducción a los Algoritmos y Estructuras de Datos

## ¿Qué son los algoritmos?

Un **algoritmo** es un conjunto de instrucciones definidas, ordenadas y finitas que permiten realizar una tarea o resolver un problema. Son fundamentales en la informática porque proporcionan una secuencia clara de pasos para lograr un objetivo específico.

### Características de los algoritmos:
- Finito: debe terminar después de un número limitado de pasos.
- Definido: cada paso debe estar claramente especificado.
- Entrada: puede tener cero o más datos de entrada.
- Salida: debe producir al menos una salida.
- Preciso: cada instrucción debe poder realizarse en un tiempo finito.

### Ejemplo en pseudocódigo:
**Encontrar el mayor de dos números:**

```

Inicio
Leer número A
Leer número B
Si A > B entonces
Imprimir "A es mayor"
Sino
Imprimir "B es mayor"
Fin

````

### Ejemplo en Python:
```python
def encontrar_mayor(A, B):
    if A > B:
        return A
    else:
        return B

# Ejemplo de uso
A = 5
B = 3
mayor = encontrar_mayor(A, B)
print(f"El mayor de {A} y {B} es {mayor}")
````

---

## ¿Qué son las estructuras de datos?

Una **estructura de datos** es una manera de organizar, gestionar y almacenar datos para que se pueda acceder a ellos y modificarlos de forma eficiente.

### Tipos:

* **Primitivos**: enteros, flotantes, booleanos, caracteres.
* **No primitivos**: listas, pilas, colas, árboles, grafos.

---

## Importancia de los algoritmos y estructuras de datos

* Mejoran la eficiencia de un programa.
* Permiten descomponer problemas complejos.
* Se pueden reutilizar en varios proyectos.
* Facilitan el mantenimiento del código.

---

## Ejemplos de la vida real

### 1. Motores de búsqueda

```python
def busqueda_lineal(lista, objetivo):
    for i in range(len(lista)):
        if lista[i] == objetivo:
            return i
    return -1

lista = [3, 1, 4, 1, 5, 9, 2, 6, 5]
objetivo = 5
indice = busqueda_lineal(lista, objetivo)
print(f"El objetivo {objetivo} está en el índice {indice}")
```

---

### 2. Redes sociales (Grafo)

```python
grafo = {
    "Alice": ["Bob", "Cathy"],
    "Bob": ["Alice", "Cathy", "Daisy"],
    "Cathy": ["Alice", "Bob"],
    "Daisy": ["Bob"]
}

def amigos_comunes(grafo, persona1, persona2):
    return set(grafo[persona1]) & set(grafo[persona2])

persona1 = "Alice"
persona2 = "Bob"
comunes = amigos_comunes(grafo, persona1, persona2)
print(f"Amigos comunes entre {persona1} y {persona2}: {comunes}")
```

---

### 3. Comercio electrónico (Recomendación)

```python
productos = {
    "producto1": [5, 4, 3],
    "producto2": [3, 4, 2],
    "producto3": [4, 5, 5]
}

def calificacion_promedio(producto):
    calificaciones = productos[producto]
    return sum(calificaciones) / len(calificaciones)

for producto in productos:
    print(f"La calificación promedio de {producto} es {calificacion_promedio(producto)}")
```

---

### 4. Navegación GPS (Dijkstra)

```python
import heapq

def dijkstra(grafo, inicio):
    distancias = {nodo: float('inf') for nodo in grafo}
    distancias[inicio] = 0
    pq = [(0, inicio)]

    while pq:
        dist_actual, nodo_actual = heapq.heappop(pq)

        if dist_actual > distancias[nodo_actual]:
            continue

        for vecino, peso in grafo[nodo_actual].items():
            distancia = dist_actual + peso
            if distancia < distancias[vecino]:
                distancias[vecino] = distancia
                heapq.heappush(pq, (distancia, vecino))

    return distancias

grafo = {
    'A': {'B': 1, 'C': 4},
    'B': {'A': 1, 'C': 2, 'D': 5},
    'C': {'A': 4, 'B': 2, 'D': 1},
    'D': {'B': 5, 'C': 1}
}

inicio = 'A'
distancias = dijkstra(grafo, inicio)
print(f"Distancias desde {inicio}: {distancias}")
```

---

## Python como herramienta para estudiar algoritmos y estructuras de datos

### Ventajas:

* Sintaxis clara.
* Bibliotecas como `collections` y `heapq`.
* Interactivo y educativo.
* Gran comunidad.

### Ejemplo de uso de estructuras básicas en Python

#### Listas

```python
numeros = [3, 1, 4, 1, 5, 9]
print("Máximo:", max(numeros))
print("Ordenada:", sorted(numeros))
```

#### Cola (FIFO)

```python
from collections import deque

cola = deque()
cola.append(1)
cola.append(2)
cola.append(3)
print("Salida:", cola.popleft())
print("Cola:", list(cola))
```

#### Pila (LIFO)

```python
pila = []
pila.append(1)
pila.append(2)
pila.append(3)
print("Salida:", pila.pop())
print("Pila:", pila)
```

#### Diccionario para contar frecuencias

```python
elementos = ['a', 'b', 'a', 'c', 'b', 'a']
frecuencia = {}

for e in elementos:
    if e in frecuencia:
        frecuencia[e] += 1
    else:
        frecuencia[e] = 1

print("Frecuencia:", frecuencia)
```

---

# Examen: Introducción a los Algoritmos y Estructuras de Datos

1. ¿Qué es un algoritmo y cuáles son sus características principales?
2. Da un ejemplo de un algoritmo simple en pseudocódigo.
3. Explica por qué es importante que un algoritmo sea finito.
4. Proporciona un ejemplo de un algoritmo que no es finito.
5. ¿Qué se entiende por entrada y salida en un algoritmo?
6. Da un ejemplo de un algoritmo con múltiples entradas y una salida.
7. Enumera y describe las estructuras de datos primitivas más comunes en Python.
8. Proporciona ejemplos de uso en Python para cada una de ellas.
9. Define qué son las estructuras de datos no primitivas y da ejemplos.
10. Describe cómo se utiliza una lista enlazada y proporciona un código de ejemplo en Python.
11. ¿Por qué es importante considerar la eficiencia de un algoritmo?
12. Explica la diferencia entre búsqueda lineal y búsqueda binaria con ejemplos en Python.
13. Da dos ejemplos de cómo los algoritmos son utilizados en motores de búsqueda.
14. Explica cómo se utilizan los algoritmos en las redes sociales para recomendar amigos.
15. Describe cómo funcionan los algoritmos de recomendación en plataformas de comercio electrónico.
16. Proporciona un ejemplo simple de un algoritmo de recomendación en Python.
17. Explica el uso de grafos en sistemas de navegación GPS.
18. Implementa el algoritmo de Dijkstra en Python para encontrar la ruta más corta entre dos puntos.
19. ¿Por qué Python es una herramienta útil para estudiar algoritmos y estructuras de datos?
20. Da ejemplos de uso de listas, colas y pilas en Python.

---

