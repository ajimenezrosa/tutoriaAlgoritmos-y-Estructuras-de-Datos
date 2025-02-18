**Libro de Texto: Algoritmos y Estructuras de Datos**

**Autor: José Alejandro Jiménez Rosa**

---

# **Prólogo**
Bienvenidos al libro de texto de la materia *Algoritmos y Estructuras de Datos*. Este material ha sido diseñado para guiar a los estudiantes en el estudio de los fundamentos de la programación y la manipulación eficiente de datos. A lo largo de este libro, exploraremos los conceptos clave, implementaciones prácticas y análisis de eficiencia de los algoritmos más importantes en la informática.

Este libro está dirigido a estudiantes que no tienen conocimientos previos en programación. Cada concepto se explicará de forma detallada y con ejemplos ilustrativos que ayudarán a comprender mejor cada tema.

---

# **Capítulo 1: Introducción a los Algoritmos**
**Fecha: Lunes 19 de febrero de 2025**

[...] (contenido existente)

---

# **Capítulo 5: Programación Dinámica y Recursión**
**Fecha: Lunes 18 de marzo de 2025**

## **Recursión vs Iteración**
La recursión es una técnica en la que una función se llama a sí misma hasta alcanzar una condición base. Es útil cuando un problema puede dividirse en subproblemas similares.

### **Ejemplo 1: Factorial con Recursión**
```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))  # Salida: 120
```

### **Ejemplo 2: Fibonacci con Memorización**
```python
def fibonacci(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 2:
        return 1
    memo[n] = fibonacci(n-1, memo) + fibonacci(n-2, memo)
    return memo[n]

print(fibonacci(10))  # Salida: 55
```

### **Aplicaciones en el mundo real**
Se usa en optimización de rutas, teoría de juegos y procesamiento de texto.

---

# **Capítulo 6: Algoritmos Voraces (Greedy)**
**Fecha: Lunes 25 de marzo de 2025**

Los algoritmos voraces toman decisiones en cada paso basándose en la mejor opción disponible sin considerar el futuro.

### **Ejemplo 1: Problema del Cambio de Monedas**
```python
def cambio_monedas(monedas, cantidad):
    resultado = []
    monedas.sort(reverse=True)
    for moneda in monedas:
        while cantidad >= moneda:
            cantidad -= moneda
            resultado.append(moneda)
    return resultado

print(cambio_monedas([1, 5, 10, 25], 63))  # Salida: [25, 25, 10, 1, 1, 1]
```

### **Ejemplo 2: Algoritmo de Huffman para Compresión de Datos**
```python
import heapq
class NodoHuffman:
    def __init__(self, simbolo, frecuencia):
        self.simbolo = simbolo
        self.frecuencia = frecuencia
        self.izquierda = None
        self.derecha = None

def construir_arbol(frecuencias):
    cola = [NodoHuffman(s, f) for s, f in frecuencias.items()]
    heapq.heapify(cola)
    while len(cola) > 1:
        izq = heapq.heappop(cola)
        der = heapq.heappop(cola)
        nodo = NodoHuffman(None, izq.frecuencia + der.frecuencia)
        nodo.izquierda = izq
        nodo.derecha = der
        heapq.heappush(cola, nodo)
    return cola[0]
```

### **Aplicaciones en el mundo real**
Se usa en compresión de datos, planificación y problemas de optimización.

---

# **Capítulo 7: Algoritmos de Grafos**
**Fecha: Lunes 1 de abril de 2025**

Los grafos modelan redes como carreteras, redes sociales y telecomunicaciones.

## **Ejemplo 1: Algoritmo de Dijkstra**
```python
import heapq

def dijkstra(grafo, inicio):
    distancias = {nodo: float('inf') for nodo in grafo}
    distancias[inicio] = 0
    cola = [(0, inicio)]
    while cola:
        actual_distancia, actual_nodo = heapq.heappop(cola)
        for vecino, peso in grafo[actual_nodo].items():
            distancia = actual_distancia + peso
            if distancia < distancias[vecino]:
                distancias[vecino] = distancia
                heapq.heappush(cola, (distancia, vecino))
    return distancias
```

### **Ejemplo 2: Búsqueda en Anchura (BFS)**
```python
from collections import deque

def bfs(grafo, inicio):
    visitados = set()
    cola = deque([inicio])
    while cola:
        nodo = cola.popleft()
        if nodo not in visitados:
            print(nodo, end=' ')
            visitados.add(nodo)
            cola.extend(grafo[nodo] - visitados)
```

### **Aplicaciones en el mundo real**
Usado en GPS, redes de telecomunicaciones y redes sociales.

---

# **Proyecto Final**
**Fecha de entrega: Lunes 1 de abril de 2025**

Cada estudiante desarrollará un proyecto final aplicando los conceptos aprendidos a un problema real, utilizando estructuras de datos y algoritmos eficientes.

---

Este libro incluye contenido detallado, múltiples ejemplos de código, ejercicios prácticos y cuestionarios para reforzar el aprendizaje. ¡Déjame saber si necesitas más mejoras!

