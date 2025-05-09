# **Libro de Texto: Algoritmos y Estructuras de Datos**

## **Autor: José Alejandro Jiménez Rosa**

# Capítulo 1: Introducción a los Algoritmos y Estructuras de Datos

## 1.1 ¿Qué es un algoritmo?

Un **algoritmo** es una secuencia ordenada y finita de pasos definidos que resuelven un problema o ejecutan una tarea específica. Los algoritmos son el fundamento de la programación informática, ya que permiten expresar de manera lógica y sistemática la solución a un problema.

### Características de un algoritmo

Un algoritmo debe cumplir con las siguientes características fundamentales:

* **Finito:** debe terminar en un número limitado de pasos.
* **Definido:** cada instrucción debe ser clara y no ambigua.
* **Entrada:** puede recibir cero o más datos de entrada.
* **Salida:** debe producir al menos una salida o resultado.
* **Eficiente:** debe ser posible ejecutarlo en un tiempo razonable.

### Ejemplo de algoritmo en pseudocódigo

**Problema:** Encontrar el mayor de dos números.

```
Inicio
  Leer número A
  Leer número B
  Si A > B entonces
    Imprimir "A es mayor"
  Sino
    Imprimir "B es mayor"
Fin
```

### Implementación en Python

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
```

---

## 1.2 ¿Qué son las estructuras de datos?

Una **estructura de datos** es una forma organizada de almacenar y manipular información en un programa de manera eficiente. Son esenciales para implementar algoritmos de manera eficaz.

### Clasificación

* **Primitivas:** enteros, flotantes, booleanos, caracteres.
* **No primitivas:** listas, pilas, colas, árboles, grafos, tablas hash.

---

## 1.3 Importancia de los algoritmos y estructuras de datos

Los algoritmos y las estructuras de datos permiten:

* Mejorar el rendimiento del software.
* Resolver problemas complejos dividiéndolos en subproblemas.
* Reutilizar soluciones en diferentes contextos.
* Facilitar el mantenimiento del código.

---

## 1.4 Aplicaciones en la vida real

### 1.4.1 Motores de búsqueda

Usan algoritmos de búsqueda y estructuras como índices invertidos y grafos para procesar millones de páginas rápidamente.

```python
def busqueda_lineal(lista, objetivo):
    for i in range(len(lista)):
        if lista[i] == objetivo:
            return i
    return -1
```

### 1.4.2 Redes sociales

Utilizan **grafos** para representar conexiones entre usuarios.

```python
grafo = {
    "Alice": ["Bob", "Cathy"],
    "Bob": ["Alice", "Cathy", "Daisy"],
    "Cathy": ["Alice", "Bob"],
    "Daisy": ["Bob"]
}

def amigos_comunes(grafo, persona1, persona2):
    return set(grafo[persona1]) & set(grafo[persona2])
```

### 1.4.3 Comercio electrónico

Emplean algoritmos de recomendación y estructuras de datos para personalizar la experiencia del usuario.

```python
productos = {
    "producto1": [5, 4, 3],
    "producto2": [3, 4, 2],
    "producto3": [4, 5, 5]
}

def calificacion_promedio(producto):
    calificaciones = productos[producto]
    return sum(calificaciones) / len(calificaciones)
```

### 1.4.4 Navegación GPS

Los sistemas GPS como Google Maps utilizan algoritmos como **Dijkstra** para encontrar rutas óptimas.

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
```

---

## 1.5 Python como herramienta para el estudio

Python es ideal para el aprendizaje de algoritmos por su sintaxis clara, bibliotecas avanzadas y su entorno interactivo.

### Ejemplos prácticos:

#### Listas

```python
numeros = [3, 1, 4, 1, 5, 9]
print("Máximo:", max(numeros))
print("Ordenada:", sorted(numeros))
```

#### Colas

```python
from collections import deque

cola = deque([1, 2, 3])
print("Elemento retirado:", cola.popleft())
```

#### Pilas

```python
pila = [1, 2, 3]
print("Elemento retirado:", pila.pop())
```

#### Diccionarios (conteo de frecuencia)

```python
elementos = ['a', 'b', 'a', 'c', 'b', 'a']
frecuencia = {}
for e in elementos:
    frecuencia[e] = frecuencia.get(e, 0) + 1
print("Frecuencia:", frecuencia)
```

---

## Preguntas de repaso (Examen)

1. ¿Qué es un algoritmo y cuáles son sus características principales?
2. Da un ejemplo de un algoritmo simple en pseudocódigo.
3. ¿Por qué es importante que un algoritmo sea finito?
4. Proporciona un ejemplo de un algoritmo que no sea finito.
5. ¿Qué se entiende por entrada y salida en un algoritmo?
6. Da un ejemplo de un algoritmo con múltiples entradas y una salida.
7. Enumera las estructuras de datos primitivas más comunes en Python.
8. Proporciona ejemplos en Python de listas, colas, pilas y diccionarios.
9. Define estructuras de datos no primitivas y da dos ejemplos.
10. ¿Qué es una lista enlazada? Proporcione código en Python.
11. ¿Por qué es importante la eficiencia de un algoritmo?
12. Explica la diferencia entre búsqueda lineal y binaria con ejemplos.
13. Describe dos usos de algoritmos en motores de búsqueda.
14. ¿Cómo usan las redes sociales algoritmos para sugerir amistades?
15. ¿Cómo funcionan los algoritmos de recomendación en e-commerce?
16. Proporciona un ejemplo simple de recomendación en Python.
17. Explica cómo se aplican los grafos en navegación GPS.
18. Implementa el algoritmo de Dijkstra en Python.
19. ¿Por qué Python es útil para aprender estos temas?
20. Muestra un ejemplo de uso de listas, colas y pilas.

---
