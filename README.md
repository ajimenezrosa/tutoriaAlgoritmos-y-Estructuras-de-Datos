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

## Examen: Introducción a los Algoritmos y Estructuras de Datos

### Definición de Algoritmos:

1. ¿Qué es un algoritmo y cuáles son sus características principales?
2. Da un ejemplo de un algoritmo simple en pseudo código.

### Finitud de los Algoritmos:

3. Explica por qué es importante que un algoritmo sea finito.
4. Proporciona un ejemplo de un algoritmo que no es finito.

### Entrada y Salida en Algoritmos:

5. ¿Qué se entiende por entrada y salida en un algoritmo?
6. Da un ejemplo de un algoritmo con múltiples entradas y una salida.

### Estructuras de Datos Primitivas:

7. Enumera y describe las estructuras de datos primitivas más comunes en Python.
8. Proporciona ejemplos de uso en Python para cada una de ellas.

### Estructuras de Datos No Primitivas:

9. Define qué son las estructuras de datos no primitivas y da ejemplos.
10. Describe cómo se utiliza una lista enlazada y proporciona un código de ejemplo en Python.

### Eficiencia en Algoritmos:

11. ¿Por qué es importante considerar la eficiencia de un algoritmo?
12. Explica la diferencia entre búsqueda lineal y búsqueda binaria con ejemplos en Python.

### Aplicaciones de Algoritmos en la Vida Real:

13. Da dos ejemplos de cómo los algoritmos son utilizados en motores de búsqueda.
14. Explica cómo se utilizan los algoritmos en las redes sociales para recomendar amigos.

### Algoritmos de Recomendación:

15. Describe cómo funcionan los algoritmos de recomendación en plataformas de comercio electrónico.
16. Proporciona un ejemplo simple de un algoritmo de recomendación en Python.

### Algoritmos de Navegación GPS:

17. Explica el uso de grafos en sistemas de navegación GPS.
18. Implementa el algoritmo de Dijkstra en Python para encontrar la ruta más corta entre dos puntos.

### Python para Algoritmos y Estructuras de Datos:

19. ¿Por qué Python es una herramienta útil para estudiar algoritmos y estructuras de datos?
20. Da ejemplos de uso de listas, colas y pilas en Python.

---





### Capítulo 2: Conceptos Básicos de Python<a name="2"></a>

Python es un lenguaje de programación de alto nivel y de propósito general que se destaca por su simplicidad y legibilidad. En este capítulo, aprenderemos los conceptos básicos de Python que son fundamentales para implementar y entender algoritmos y estructuras de datos.

#### Sintaxis básica<a name="21"></a>

Python tiene una sintaxis limpia y sencilla que facilita la lectura y escritura del código. A continuación, se presentan algunos conceptos básicos de la sintaxis de Python.

##### Variables y tipos de datos<a name="22"></a>

En Python, no es necesario declarar el tipo de una variable antes de usarla. La asignación de un valor a una variable se realiza con el operador `=`.

**Ejemplo:**

```python
# Variables y tipos de datos
entero = 10
flotante = 3.14
cadena = "Hola, Mundo"
booleano = True

print(entero)
print(flotante)
print(cadena)
print(booleano)
```

##### Operadores

Python soporta varios tipos de operadores:

1. **Aritméticos:** `+`, `-`, `*`, `/`, `//` (división entera), `%` (módulo), `**` (potencia)
2. **Relacionales:** `==`, `!=`, `>`, `<`, `>=`, `<=`
3. **Lógicos:** `and`, `or`, `not`
4. **Asignación:** `=`, `+=`, `-=`, `*=`, `/=`, `//=`, `%=`, `**=`

**Ejemplo:**

```python
a = 5
b = 3

# Operadores aritméticos
print(a + b)  # 8
print(a - b)  # 2
print(a * b)  # 15
print(a / b)  # 1.666...
print(a // b) # 1
print(a % b)  # 2
print(a ** b) # 125

# Operadores relacionales
print(a == b)  # False
print(a != b)  # True
print(a > b)   # True
print(a < b)   # False
print(a >= b)  # True
print(a <= b)  # False

# Operadores lógicos
print(a > 2 and b < 5)  # True
print(a > 2 or b > 5)   # True
print(not(a > 2))       # False
```

#### Estructuras de control<a name="23"></a>

Python proporciona varias estructuras de control para el flujo de ejecución del programa.

##### Condicionales

La estructura condicional `if`, `elif` y `else` se usa para tomar decisiones basadas en condiciones.

**Ejemplo:**

```python
x = 10

if x > 0:
    print("x es positivo")
elif x < 0:
    print("x es negativo")
else:
    print("x es cero")
```

##### Bucles

Python soporta dos tipos de bucles: `for` y `while`.

**Bucle `for`:**

```python
# Bucle for
for i in range(5):
    print(i)
```

**Bucle `while`:**

```python
# Bucle while
i = 0
while i < 5:
    print(i)
    i += 1
```

#### Funciones y módulos<a name="24"></a>

Las funciones son bloques de código reutilizables que realizan una tarea específica. Se definen usando la palabra clave `def`.

**Ejemplo:**

```python
def suma(a, b):
    return a + b

resultado = suma(3, 5)
print(resultado)  # 8
```

Los módulos son archivos que contienen definiciones y declaraciones de Python. Puedes importar un módulo usando la palabra clave `import`.

**Ejemplo:**

```python
import math

print(math.sqrt(16))  # 4.0
```

---

### Ejercicios

1. **Variables y Operadores:**
    - Define dos variables con valores enteros y realiza operaciones aritméticas básicas (suma, resta, multiplicación, división).
      **Descripción:** 
      Define dos variables enteras y usa los operadores aritméticos para realizar las operaciones mencionadas. Imprime los resultados.
      **Ejemplo:**
      ```python
      a = 10
      b = 5
      print(a + b)  # 15
      print(a - b)  # 5
      print(a * b)  # 50
      print(a / b)  # 2.0
      ```
    - Define una variable de tipo cadena y usa operadores de concatenación para unirla con otra cadena.
      **Descripción:**
      Crea dos variables de tipo cadena y únelas usando el operador `+`. Imprime el resultado.
      **Ejemplo:**
      ```python
      saludo = "Hola"
      nombre = "Mundo"
      mensaje = saludo + ", " + nombre
      print(mensaje)  # Hola, Mundo
      ```

2. **Condicionales:**
    - Escribe un programa que tome un número como entrada y determine si es positivo, negativo o cero.
      **Descripción:**
      Usa la estructura `if-elif-else` para evaluar el valor de una variable y determinar si es positivo, negativo o cero. Imprime el resultado.
      **Ejemplo:**
      ```python
      numero = int(input("Introduce un número: "))
      if numero > 0:
          print("El número es positivo")
      elif numero < 0:
          print("El número es negativo")
      else:
          print("El número es cero")
      ```
    - Escribe un programa que tome la edad de una persona como entrada y determine si es un niño, un adolescente, un adulto o un anciano.
      **Descripción:**
      Usa la estructura `if-elif-else` para evaluar la edad y categorizarla en niño, adolescente, adulto o anciano. Imprime el resultado.
      **Ejemplo:**
      ```python
      edad = int(input("Introduce tu edad: "))
      if edad < 13:
          print("Eres un niño")
      elif edad < 20:
          print("Eres un adolescente")
      elif edad < 65:
          print("Eres un adulto")
      else:
          print("Eres un anciano")
      ```

3. **Bucles:**
    - Escribe un programa que imprima los números del 1 al 10 usando un bucle `for`.
      **Descripción:**
      Usa un bucle `for` con la función `range` para iterar del 1 al 10 e imprime cada número.
      **Ejemplo:**
      ```python
      for i in range(1, 11):
          print(i)
      ```
    - Escribe un programa que imprima los números del 1 al 10 usando un bucle `while`.
      **Descripción:**
      Usa un bucle `while` para iterar del 1 al 10 e imprime cada número.
      **Ejemplo:**
      ```python
      i = 1
      while i <= 10:
          print(i)
          i += 1
      ```

4. **Funciones:**
    - Define una función que tome dos números como parámetros y devuelva su producto.
      **Descripción:**
      Define una función que reciba dos parámetros, calcule su producto y retorne el resultado.
      **Ejemplo:**
      ```python
      def producto(a, b):
          return a * b

      resultado = producto(4, 5)
      print(resultado)  # 20
      ```
    - Define una función que tome una cadena como parámetro y devuelva la cadena en mayúsculas.
      **Descripción:**
      Define una función que reciba una cadena como parámetro y use el método `upper` para convertirla a mayúsculas. Retorna el resultado.
      **Ejemplo:**
      ```python
      def convertir_mayusculas(cadena):
          return cadena.upper()

      resultado = convertir_mayusculas("hola")
      print(resultado)  # HOLA
      ```

5. **Módulos:**
    - Usa el módulo `random` para generar un número aleatorio entre 1 y 100.
      **Descripción:**
      Importa el módulo `random` y usa la función `randint` para generar un número aleatorio entre 1 y 100. Imprime el resultado.
      **Ejemplo:**
      ```python
      import random
      numero_aleatorio = random.randint(1, 100)
      print(numero_aleatorio)
      ```
    - Usa el módulo `datetime` para imprimir la fecha y hora actuales.
      **Descripción:**
      Importa el módulo `datetime` y usa la función `now` para obtener la fecha y hora actuales. Imprime el resultado.
      **Ejemplo:**
      ```python
      from datetime import datetime
      fecha_hora_actual = datetime.now()
      print(fecha_hora_actual)
      ```

---

### Examen: Conceptos Básicos de Python

1. **Variables:**
    - **Pregunta:** ¿Cómo se define una variable en Python y cómo se asigna un valor? Da un ejemplo.
      <!-- **Respuesta:** Se define una variable simplemente asignándole un valor usando el operador `=`. Ejemplo:
      ```python
      x = 10
      ```
      **Justificación:** En Python, no es necesario declarar explícitamente el tipo de la variable, se infiere del valor asignado. -->

2. **Tipos de datos:**
    - **Pregunta:** Enumera los tipos de datos  básicos en Python y proporciona un ejemplo de cada uno.
      <!-- **Respuesta:** Enteros (`int`), flotantes (`float`), cadenas (`str`), booleanos (`bool`).
      ```python
      entero = 10
      flotante = 3.14
      cadena = "Hola"
      booleano = True
      ```
      **Justificación:** Estos son los tipos de datos fundamentales en Python, que cubren las necesidades básicas de almacenamiento de datos. -->

3. **Operadores aritméticos:**
    - **Pregunta:** ¿Cuáles son los operadores aritméticos en Python? Da un ejemplo de cada uno.
      <!-- **Respuesta:** `+`, `-`, `*`, `/`, `//`, `%`, `**`.
      ```python
      a = 5
      b = 2
      print(a + b)  # 7
      print(a - b)  # 3
      print(a * b)  # 10
      print(a / b)  # 2.5
      print(a // b) # 2
      print(a % b)  # 1
      print(a ** b) # 25
      ```
      **Justificación:** Estos operadores permiten realizar operaciones matemáticas básicas en Python. -->

4. **Condicionales:**
    - **Pregunta:** Escribe un ejemplo de una estructura condicional `if-elif-else`.
      <!-- **Respuesta:**
      ```python
      x = 10
      if x > 0:
          print("x es positivo")
      elif x < 0:
          print("x es negativo")
      else:
          print("x es cero")
      ```
      **Justificación:** Esta estructura permite tomar decisiones basadas en condiciones específicas. -->

5. **Bucles `for`:**
    - **Pregunta:** ¿Cómo se usa un bucle `for` en Python? Da un ejemplo.
      <!-- **Respuesta:**
      ```python
      for i in range(5):
          print(i)
      ```
      **Justificación:** Un bucle `for` se utiliza para iterar sobre una secuencia de valores. -->

6. **Bucles `while`:**
    - **Pregunta:** ¿Cómo se usa un bucle `while` en Python? Da un ejemplo.
      <!-- **Respuesta:**
      ```python
      i = 0
      while i < 5:
          print(i)
          i += 1
      ```
      **Justificación:** Un bucle `while` se utiliza para repetir una acción mientras una condición sea verdadera. -->

7. **Funciones:**
    - **Pregunta:** ¿Cómo se define una función en Python? Da un ejemplo.
      <!-- **Respuesta:**
      ```python
      def suma(a, b):
          return a + b

      resultado = suma(3, 5)
      print(resultado)  # 8
      ```
      **Justificación:** Las funciones permiten encapsular código reutilizable que realiza una tarea específica. -->

8. **Módulos:**
    - **Pregunta:** ¿Cómo se importa un módulo en Python y cómo se usa una función de ese módulo? Da un ejemplo.
      <!-- **Respuesta:**
      ```python
      import math
      print(math.sqrt(16))  # 4.0
      ```
      **Justificación:** Los módulos permiten organizar el código y reutilizar funciones y clases definidas en otros archivos. -->

9. **Operadores lógicos:**
    - **Pregunta:** Enumera los operadores lógicos en Python y proporciona un ejemplo de cada uno.
      <!-- **Respuesta:** `and`, `or`, `not`.
      ```python
      a = True
      b = False
      print(a and b)  # False
      print(a or b)   # True
      print(not a)    # False
      ```
      **Justificación:** Los operadores lógicos permiten combinar condiciones y tomar decisiones basadas en múltiples criterios. -->

10. **Estructuras de control:**
    - **Pregunta:** Escribe un programa que determine si un número es par o impar usando una estructura condicional.
      <!-- **Respuesta:**
      ```python
      numero = 7
      if numero % 2 == 0:
          print("El número es par")
      else:
          print("El número es impar")
      ```
      **Justificación:** Esta estructura condicional permite evaluar si un número es divisible por 2 y determinar si es par o impar. -->

---

Este capítulo desarrolla los conceptos básicos de Python, proporcionando una base sólida para el estudio de algoritmos y estructuras de datos. Los ejercicios, ahora con descripciones de cómo hacerlos, y el examen con respuestas correctas y justificaciones, ayudan a reforzar el aprendizaje y a evaluar la comprensión de los conceptos presentados.
