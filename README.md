# **Libro de Texto: Algoritmos y Estructuras de Datos**

## **Autor: José Alejandro Jiménez Rosa**

### ***Indices***
- [Capítulo 1: Introducción a los Algoritmos y Estructuras de Datos](#1)
- [ Capítulo 2: Conceptos Básicos de Python](#2)
- [Capítulo 3: Estructuras de Datos Lineales](#3)
- [Capítulo 4: Estructuras de Datos No Lineales](#4)

# Capítulo 1: Introducción a los Algoritmos y Estructuras de Datos<a name="1"></a>

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

### Examen: Introducción a los Algoritmos y Estructuras de Datos

1. **Definición de Algoritmos:**
    - **Pregunta:** ¿Qué es un algoritmo y cuáles son sus características principales?

      **Respuesta:** Un algoritmo es un conjunto de instrucciones definidas, ordenadas y finitas que permiten realizar una tarea o resolver un problema. Sus características principales son finitud, definición, entrada, salida y efectividad.
      
      **Justificación:** Estas características aseguran que el algoritmo sea claro, preciso y ejecutable en un tiempo finito.

    - **Pregunta:** Da un ejemplo de un algoritmo simple en pseudo código.
      **Respuesta:** 
      ```
      Iniciar.
      Leer el primer número, A.
      Leer el segundo número, B.
      Si A > B, entonces:
          Imprimir A es mayor.
      De lo contrario:
          Imprimir B es mayor.
      Fin.
      ```
      **Justificación:** Este ejemplo muestra un algoritmo básico para comparar dos números.

2. **Finitud de los Algoritmos:**
    - **Pregunta:** Explica por qué es importante que un algoritmo sea finito.
     
      **Respuesta:** Es importante porque un algoritmo debe terminar después de un número finito de pasos para ser útil y práctico.
     
      **Justificación:** Un algoritmo infinito no proporciona una solución en un tiempo razonable, haciendo imposible resolver el problema.
    
    - **Pregunta:** Proporciona un ejemplo de un algoritmo que no es finito.
     
      **Respuesta:** 
      ```
      Iniciar.
      Mientras (verdadero):
          Imprimir "Hola".
      Fin.
      ```
    
      **Justificación:** Este algoritmo no tiene una condición de terminación y se ejecutará indefinidamente.

3. **Entrada y Salida en Algoritmos:**
    - **Pregunta:** ¿Qué se entiende por entrada y salida en un algoritmo?
    
      **Respuesta:** La entrada es la información inicial que el algoritmo necesita para comenzar. La salida es el resultado final que el algoritmo produce después de procesar la entrada.
   
      **Justificación:** La entrada y salida son fundamentales para definir el propósito y el resultado del algoritmo.
   
    - **Pregunta:** Da un ejemplo de un algoritmo con múltiples entradas y una salida.
 
      **Respuesta:**
      ```
      Iniciar.
      Leer número A.
      Leer número B.
      Leer número C.
      Sumar A, B y C.
      Imprimir la suma.
      Fin.
      ```
   
      **Justificación:** Este ejemplo muestra cómo un algoritmo puede procesar múltiples entradas para producir una única salida.

4. **Estructuras de Datos Primitivas:**
   
    - **Pregunta:** Enumera y describe las estructuras de datos primitivas más comunes en Python.
   
      **Respuesta:** Enteros (`int`), flotantes (`float`), caracteres (`str`), booleanos (`bool`).
   
      **Justificación:** Estas estructuras básicas son esenciales para almacenar y manipular datos simples en Python.
   
    - **Pregunta:** Proporciona ejemplos de uso en Python para cada una de ellas.
   
      **Respuesta:**
      ```python
      # Entero
      numero = 10
      # Flotante
      decimal = 3.14
      # Caracter
      letra = 'a'
      # Booleano
      es_verdadero = True
      ```
   
      **Justificación:** Estos ejemplos muestran cómo definir y usar cada tipo de dato primitivo en Python.

5. **Estructuras de Datos No Primitivas:**
  
    - **Pregunta:** Define qué son las estructuras de datos no primitivas y da ejemplos.
  
      **Respuesta:** Son estructuras que se componen de múltiples elementos de datos. Ejemplos incluyen listas, pilas, colas, árboles y grafos.
  
      **Justificación:** Estas estructuras permiten almacenar y organizar datos complejos de manera eficiente.
 
    - **Pregunta:** Describe cómo se utiliza una lista enlazada y proporciona un código de ejemplo en Python.
 
      **Respuesta:** Una lista enlazada es una colección de nodos donde cada nodo contiene un valor y una referencia al siguiente nodo en la secuencia.
      ```python
      class Nodo:
          def __init__(self, dato=None):
              self.dato = dato
              self.siguiente = None

      class ListaEnlazada:
          def __init__(self):
              self.cabeza = None

          def agregar(self, dato):
              nuevo_nodo = Nodo(dato)
              nuevo_nodo.siguiente = self.cabeza
              self.cabeza = nuevo_nodo

          def mostrar(self):
              nodo_actual = self.cabeza
              while nodo_actual:
                  print(nodo_actual.dato)
                  nodo_actual = nodo_actual.siguiente

      # Ejemplo de uso
      lista = ListaEnlazada()
      lista.agregar(3)
      lista.agregar(2)
      lista.agregar(1)
      lista.mostrar()
      ```
 
      **Justificación:** Este ejemplo muestra cómo implementar y usar una lista enlazada en Python.

6. **Eficiencia en Algoritmos:**
   
    - **Pregunta:** ¿Por qué es importante considerar la eficiencia de un algoritmo?
 
      **Respuesta:** La eficiencia determina cuán rápido y con cuánta memoria un algoritmo puede resolver un problema, lo cual es crucial en aplicaciones con grandes volúmenes de datos o en tiempo real.
  
      **Justificación:** Algoritmos eficientes mejoran el rendimiento y reducen los costos computacionales.
 
    - **Pregunta:** Explica la diferencia entre búsqueda lineal y búsqueda binaria con ejemplos en Python.
 
      **Respuesta:** 
      ```python
      # Búsqueda lineal
      def busqueda_lineal(lista, objetivo):
          for i in range(len(lista)):
              if lista[i] == objetivo:
                  return i
          return -1

      # Búsqueda binaria
      def busqueda_binaria(lista, objetivo):
          inicio = 0
          fin = len(lista) - 1
          while inicio <= fin:
              medio = (inicio + fin) // 2
              if lista[medio] == objetivo:
                  return medio
              elif lista[medio] < objetivo:
                  inicio = medio + 1
              else:
                  fin = medio - 1
          return -1

      # Ejemplo de uso
      lista = [1, 2, 3, 4, 5, 6, 7, 8, 9]
      objetivo = 5
      print(busqueda_lineal(lista, objetivo))  # Salida: 4
      print(busqueda_binaria(lista, objetivo))  # Salida: 4
      ```

      **Justificación:** La búsqueda lineal recorre secuencialmente la lista, mientras que la búsqueda binaria divide la lista ordenada y reduce la cantidad de elementos a buscar en cada paso.

7. **Aplicaciones de Algoritmos en la Vida Real:**
 
    - **Pregunta:** Da dos ejemplos de cómo los algoritmos son utilizados en motores de búsqueda.

      **Respuesta:** Los algoritmos de PageRank determinan la relevancia de una página web, y los algoritmos de búsqueda rápida proporcionan resultados en milisegundos.
 
      **Justificación:** Estos algoritmos permiten a los motores de búsqueda organizar y presentar información de manera eficiente.

    - **Pregunta:** Explica cómo se utilizan los algoritmos en las redes sociales para recomendar amigos.
 
      **Respuesta:** Se utilizan grafos para representar relaciones entre usuarios y algoritmos de recomendación para sugerir amigos basados en amigos comunes y patrones de interacción.
 
      **Justificación:** Estos algoritmos ayudan a los usuarios a encontrar y conectar con personas relevantes.

8. **Algoritmos de Recomendación:**
  
    - **Pregunta:** Describe cómo funcionan los algoritmos de recomendación en plataformas de comercio electrónico.
 
      **Respuesta:** Analizan el historial de compras y comportamiento del usuario para predecir y sugerir productos que le puedan interesar.
 
      **Justificación:** Estos algoritmos personalizan la experiencia de compra, aumentando la satisfacción y las ventas.
 
    - **Pregunta:** Proporciona un ejemplo simple de un algoritmo de recomendación en Python.

      **Respuesta:**
      ```python
      # Lista de productos y calificaciones dadas por los usuarios
      productos = {
          "producto1": [5, 4, 3],
          "producto2": [3, 4, 2],
          "producto3": [4, 5, 5]
      }

      # Función para calcular la calificación promedio de un producto
      def calificacion_promedio(producto):
          calificaciones = productos[producto]
          return sum(calificaciones) / len(calificaciones)

      # Ejemplo de uso
      for producto in productos:
          print(f"La calificación promedio de {producto} es {calificacion_promedio(producto)}")
      ```
      **Justificación:** Este ejemplo muestra cómo calcular calificaciones promedio para recomendar productos populares.

9.

 **Algoritmos de Navegación GPS:**
    - **Pregunta:** Explica el uso de grafos en sistemas de navegación GPS.
       **Respuesta:** Los grafos representan el mapa de carreteras, donde los nodos son intersecciones y los arcos son las carreteras con sus respectivas distancias.
   
   **Justificación:** Los grafos permiten modelar eficientemente las rutas y calcular caminos óptimos.
 
  **Pregunta:** Implementa el algoritmo de Dijkstra en Python para encontrar la ruta más corta entre dos puntos.
 
 **Respuesta:**
      ```python
      import heapq

      def dijkstra(grafo, inicio):
          distancias = {nodo: float('inf') for nodo in grafo}
          distancias[inicio] = 0
          pq = [(0, inicio)]

          while pq:
              (dist_actual, nodo_actual) = heapq.heappop(pq)

              if dist_actual > distancias[nodo_actual]:
                  continue

              for vecino, peso en grafo[nodo_actual].items():
                  distancia = dist_actual + peso

                  if distancia < distancias[vecino]:
                      distancias[vecino] = distancia
                      heapq.heappush(pq, (distancia, vecino))

          return distancias

      # Ejemplo de uso
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
 **Justificación:** Este código implementa el algoritmo de Dijkstra para encontrar la ruta más corta en un grafo.

10. **Python para Algoritmos y Estructuras de Datos:**
  **Pregunta:** ¿Por qué Python es una herramienta útil para estudiar algoritmos y estructuras de datos?
 
 **Respuesta:** Por su sintaxis simple, bibliotecas integradas, interactividad y una gran comunidad de soporte.
 
 **Justificación:** Estas características facilitan el aprendizaje y la implementación de algoritmos y estructuras de datos.
 
 **Pregunta:** Da ejemplos de uso de listas, colas y pilas en Python.
 
 **Respuesta:**
      ```python
      # Lista
      lista = [1, 2, 3, 4, 5]

      # Cola utilizando collections.deque
      from collections import deque
      cola = deque()
      cola.append(1)
      cola.append(2)
      primero = cola.popleft()

      # Pila
      pila = []
      pila.append(1)
      pila.append(2)
      ultimo = pila.pop()

      print("Lista:", lista)
      print("Cola después de pop:", list(cola))
      print("Pila después de pop:", pila)
      ```
**Justificación:** Estos ejemplos muestran cómo definir y utilizar listas, colas y pilas en Python.

---

<!-- Este desarrollo proporciona respuestas correctas y justificaciones detalladas para cada pregunta del examen sobre "Introducción a los Algoritmos y Estructuras de Datos". Si necesitas más información o deseas que se profundice en algún aspecto, házmelo saber. -->
# 

# Capítulo 2: Conceptos Básicos de Python<a name="2"></a>

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
      **Respuesta:** Se define una variable simplemente asignándole un valor usando el operador `=`. Ejemplo:
      ```python
      x = 10
      ```
      **Justificación:** En Python, no es necesario declarar explícitamente el tipo de la variable, se infiere del valor asignado.

2. **Tipos de datos:**
    - **Pregunta:** Enumera los tipos de datos básicos en Python y proporciona un ejemplo de cada uno.
      **Respuesta:** Enteros (`int`), flotantes (`float`), cadenas (`str`), booleanos (`bool`).
      ```python
      entero = 10
      flotante = 3.14
      cadena = "Hola"
      booleano = True
      ```
      **Justificación:** Estos son los tipos de datos fundamentales en Python, que cubren las necesidades básicas de almacenamiento de datos.

3. **Operadores aritméticos:**
    - **Pregunta:** ¿Cuáles son los operadores aritméticos en Python? Da un ejemplo de cada uno.
      **Respuesta:** `+`, `-`, `*`, `/`, `//`, `%`, `**`.
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
      **Justificación:** Estos operadores permiten realizar operaciones matemáticas básicas en Python.

4. **Condicionales:**
    - **Pregunta:** Escribe un ejemplo de una estructura condicional `if-elif-else`.
      **Respuesta:**
      ```python
      x = 10
      if x > 0:
          print("x es positivo")
      elif x < 0:
          print("x es negativo")
      else:
          print("x es cero")
      ```
      **Justificación:** Esta estructura permite tomar decisiones basadas en condiciones específicas.

5. **Bucles `for`:**
    - **Pregunta:** ¿Cómo se usa un bucle `for` en Python? Da un ejemplo.
      **Respuesta:**
      ```python
      for i in range(5):
          print(i)
      ```
      **Justificación:** Un bucle `for` se utiliza para iterar sobre una secuencia de valores.

6. **Bucles `while`:**
    - **Pregunta:** ¿Cómo se usa un bucle `while` en Python? Da un ejemplo.
      **Respuesta:**
      ```python
      i = 0
      while i < 5:
          print(i)
          i += 1
      ```
      **Justificación:** Un bucle `while` se utiliza para repetir una acción mientras una condición sea verdadera.

7. **Funciones:**
    - **Pregunta:** ¿Cómo se define una función en Python? Da un ejemplo.
      **Respuesta:**
      ```python
      def suma(a, b):
          return a + b

      resultado = suma(3, 5)
      print(resultado)  # 8
      ```
      **Justificación:** Las funciones permiten encapsular código reutilizable que realiza una tarea específica.

8. **Módulos:**
    - **Pregunta:** ¿Cómo se importa un módulo en Python y cómo se usa una función de ese módulo? Da un ejemplo.
      **Respuesta:**
      ```python
      import math
      print(math.sqrt(16))  # 4.0
      ```
      **Justificación:** Los módulos permiten organizar el código y reutilizar funciones y clases definidas en otros archivos.

9. **Operadores lógicos:**
    - **Pregunta:** Enumera los operadores lógicos en Python y proporciona un ejemplo de cada uno.
      **Respuesta:** `and`, `or`, `not`.
      ```python
      a = True
      b = False
      print(a and b)  # False
      print(a or b)   # True
      print(not a)    # False
      ```
      **Justificación:** Los operadores lógicos permiten combinar condiciones y tomar decisiones basadas en múltiples criterios.

10. **Estructuras de control:**
    - **Pregunta:** Escribe un programa que determine si un número es par o impar usando una estructura condicional.
      **Respuesta:**
      ```python
      numero = 7
      if numero % 2 == 0:
          print("El número es par")
      else:
          print("El número es impar")
      ```
      **Justificación:** Esta estructura condicional permite evaluar si un número es divisible por 2 y determinar si es par o impar.

---

## 🧪 Examen: Conceptos Básicos de Python  
**Asignatura:** Algoritmos y Estructuras de Datos  
**Profesor:** José Alejandro Jiménez Rosa  
**Modalidad:** Selección múltiple  
**Duración:** 45 minutos  
**Instrucciones:** Selecciona la opción correcta en cada pregunta. Lee bien antes de responder.

---

### 1. ¿Cómo se define una variable en Python?

- A) `int x = 5`  
- ✅ B) `x = 5`  
- C) `define x = 5`  
- D) `variable x = 5`  

**Justificación:** En Python no se especifica el tipo; basta con usar el signo `=` para asignar un valor a una variable.

---

### 2. ¿Cuál de los siguientes es un tipo de dato básico en Python?

- A) `character`  
- B) `decimal`  
- ✅ C) `list`  
- D) `text`  

**Justificación:** Python tiene tipos como `int`, `float`, `bool`, `str` y `list`. `list` es una estructura básica de datos mutable.

---

### 3. ¿Cuál de estos es un operador aritmético en Python?

- A) `>>`  
- ✅ B) `+`  
- C) `&`  
- D) `===`  

**Justificación:** El operador `+` se usa para sumar en Python. Otros aritméticos incluyen `-`, `*`, `/`, `//`, `%`, `**`.

---

### 4. ¿Qué estructura condicional se usa para evaluar múltiples condiciones?

- A) `switch`  
- ✅ B) `if-elif-else`  
- C) `case-when`  
- D) `try-except`  

**Justificación:** `if-elif-else` permite evaluar varias condiciones secuenciales en Python.

---

### 5. ¿Qué instrucción imprime cada elemento de una lista en un bucle `for`?

- A) `for i in range(lista): print(i)`  
- B) `for print in lista:`  
- ✅ C) `for i in lista: print(i)`  
- D) `loop lista: print(i)`  

**Justificación:** La sintaxis correcta para iterar una lista es `for elemento in lista`.

---

### 6. ¿Cuál es la forma correcta de usar un bucle `while` en Python?

- A) `while x < 5 { print(x) }`  
- ✅ B) `while x < 5: print(x)`  
- C) `loop(x < 5): print(x)`  
- D) `repeat x < 5: print(x)`  

**Justificación:** Python usa `while` seguido de `:` y la indentación determina el bloque del bucle.

---

### 7. ¿Cómo se define una función en Python?

- A) `function suma(a, b): return a + b`  
- ✅ B) `def suma(a, b): return a + b`  
- C) `create suma(a, b): return a + b`  
- D) `func suma(a, b) = a + b`  

**Justificación:** En Python, las funciones se definen con la palabra clave `def`.

---

### 8. ¿Cómo se importa y usa una función del módulo `math`?
 
- A) `include math.sqrt(9)`  
- ✅ B) `import math` y luego `math.sqrt(9)`  
- C) `math = import("math")`  
- D) `using math.sqrt(9)`  

**Justificación:** Se usa `import math` y luego se accede a sus funciones con notación de punto. -->

---

### 9. ¿Cuál de estos es un operador lógico en Python?

- A) `&&`  
- ✅ B) `and`  
- C) `&!`  
- D) `xor`  

**Justificación:** Python usa `and`, `or` y `not` como operadores lógicos. No se usa `&&`.

---

### 10. ¿Cuál es el código correcto para determinar si un número es par o impar?

- A) `if numero % 2 == 1: print("Par") else: print("Impar")`  
- ✅ B) `if numero % 2 == 0: print("Par") else: print("Impar")`  
- C) `if numero // 2 == 0: print("Par")`  
- D) `if numero % 2 != 1: print("Impar")`  

**Justificación:** Un número es par si al dividirlo entre 2, el residuo (`%`) es 0.

---



Este capítulo desarrolla los conceptos básicos de Python, proporcionando una base sólida para el estudio de algoritmos y estructuras de datos. Los ejercicios, ahora con descripciones de cómo hacerlos, y el examen con respuestas correctas y justificaciones, ayudan a reforzar el aprendizaje y a evaluar la comprensión de los conceptos presentados.

# 



# Capítulo 3: Estructuras de Datos Lineales<a name="3"></a>

Las estructuras de datos lineales son fundamentales para la organización y manipulación de datos en secuencia. Este capítulo cubre las siguientes estructuras de datos lineales: listas, pilas, colas y listas enlazadas. Comprender estas estructuras y sus operaciones básicas es crucial para implementar algoritmos eficientes.

#### Listas

Las listas en Python son colecciones ordenadas y mutables de elementos. Pueden contener elementos de diferentes tipos y se utilizan ampliamente debido a su flexibilidad.

**Operaciones básicas con listas:**

1. **Creación:**
   ```python
   lista_vacia = []
   lista = [1, 2, 3, 4, 5]
   ```

2. **Acceso a elementos:**
   ```python
   primer_elemento = lista[0]  # 1
   ultimo_elemento = lista[-1]  # 5
   ```

3. **Modificación de elementos:**
   ```python
   lista[0] = 10
   ```

4. **Añadir elementos:**
   ```python
   lista.append(6)
   lista.insert(2, 15)  # Insertar 15 en la posición 2
   ```

5. **Eliminar elementos:**
   ```python
   lista.pop()  # Elimina el último elemento
   lista.remove(3)  # Elimina el primer 3 encontrado
   ```

6. **Recorrer la lista:**
   ```python
   for elemento in lista:
       print(elemento)
   ```

**Ejemplos de uso de listas:**

- Guardar una lista de nombres de estudiantes.
- Almacenar una secuencia de números en un programa de estadísticas.
- Implementar una lista de tareas pendientes.

#### Pilas (Stacks)

Las pilas son estructuras de datos que siguen el principio LIFO (Last In, First Out), donde el último elemento añadido es el primero en ser eliminado. En Python, se pueden implementar utilizando listas.

**Operaciones básicas con pilas:**

1. **Creación:**
   ```python
   pila = []
   ```

2. **Añadir elementos (push):**
   ```python
   pila.append(1)
   pila.append(2)
   ```

3. **Eliminar elementos (pop):**
   ```python
   elemento = pila.pop()  # Elimina y retorna el último elemento
   ```

4. **Obtener el elemento superior sin eliminarlo:**
   ```python
   elemento_superior = pila[-1]
   ```

**Ejemplos de uso de pilas:**

- Implementación de deshacer/rehacer en editores de texto.
- Evaluación de expresiones matemáticas.
- Manejo de llamadas a funciones y recursión.

#### Colas (Queues)

Las colas son estructuras de datos que siguen el principio FIFO (First In, First Out), donde el primer elemento añadido es el primero en ser eliminado. En Python, se pueden implementar utilizando la clase `deque` del módulo `collections`.

**Operaciones básicas con colas:**

1. **Creación:**
   ```python
   from collections import deque
   cola = deque()
   ```

2. **Añadir elementos (enqueue):**
   ```python
   cola.append(1)
   cola.append(2)
   ```

3. **Eliminar elementos (dequeue):**
   ```python
   elemento = cola.popleft()  # Elimina y retorna el primer elemento
   ```

4. **Obtener el primer elemento sin eliminarlo:**
   ```python
   primer_elemento = cola[0]
   ```

**Ejemplos de uso de colas:**

- Gestión de tareas en un servidor de impresión.
- Simulación de líneas de espera en sistemas de colas.
- Procesamiento de elementos en sistemas de mensajería.

#### Listas Enlazadas

Las listas enlazadas son colecciones de nodos donde cada nodo contiene un valor y una referencia al siguiente nodo. Se utilizan cuando se requiere una inserción y eliminación eficientes.

**Operaciones básicas con listas enlazadas:**

1. **Creación de un nodo:**
   ```python
   class Nodo:
       def __init__(self, dato):
           self.dato = dato
           self.siguiente = None
   ```

2. **Creación de una lista enlazada:**
   ```python
   class ListaEnlazada:
       def __init__(self):
           self.cabeza = None

       def agregar(self, dato):
           nuevo_nodo = Nodo(dato)
           nuevo_nodo.siguiente = self.cabeza
           self.cabeza = nuevo_nodo

       def mostrar(self):
           nodo_actual = self.cabeza
           while nodo_actual:
               print(nodo_actual.dato)
               nodo_actual = nodo_actual.siguiente
   ```

**Ejemplos de uso de listas enlazadas:**

- Implementación de estructuras de datos dinámicas como pilas y colas.
- Representación de grafos y árboles.
- Gestión de bloques de memoria en sistemas operativos.

---

### Ejemplos de Uso

**Listas:**
- Almacenar calificaciones de estudiantes y calcular el promedio.
- Gestionar un inventario de productos en una tienda.
- Registrar los movimientos de un jugador en un juego.

**Pilas:**
- Implementar una calculadora que evalúa expresiones en notación postfija.
- Gestionar la pila de llamadas en un programa recursivo.
- Realizar operaciones de retroceso en un navegador web.

**Colas:**
- Controlar el orden de llegada de clientes en un sistema de atención al cliente.
- Simular el tráfico en un sistema de simulación de tránsito.
- Procesar tareas en un sistema de procesamiento en lotes.

**Listas Enlazadas:**
- Implementar un sistema de historial de navegación.
- Crear una estructura de datos de conjunto disjunto.
- Gestionar una lista de reproducción dinámica en un reproductor de música.

---

### Examen: Estructuras de Datos Lineales

1. **¿Cuál de las siguientes opciones describe mejor una pila?**
    - A) Una estructura de datos que sigue el principio FIFO.
    - B) Una estructura de datos que sigue el principio LIFO.
    - C) Una estructura de datos que permite acceso aleatorio.
    - D) Una estructura de datos que siempre está ordenada.
    <!-- **Respuesta:** B
    **Justificación:** Una pila sigue el principio LIFO (Last In, First Out). -->

2. **¿Qué método se utiliza para eliminar el último elemento de una lista en Python?**
    - A) `remove()`
    - B) `pop()`
    - C) `delete()`
    - D) `extract()`
    <!-- **Respuesta:** B
    **Justificación:** El método `pop()` elimina y retorna el último elemento de una lista en Python. -->

3. **¿Qué estructura de datos es adecuada para implementar una cola?**
    - A) Lista
    - B) Diccionario
    - C) `deque` de `collections`
    - D) Conjunto
    <!-- **Respuesta:** C
    **Justificación:** La clase `deque` de `collections` es adecuada para implementar colas debido a su eficiencia en operaciones de inserción y eliminación en ambos extremos. -->

4. **¿Cuál es la complejidad temporal de acceder a un elemento en una lista enlazada?**
    - A) O(1)
    - B) O(log n)
    - C) O(n)
    - D) O(n log n)
    <!-- **Respuesta:** C
    **Justificación:** Acceder a un elemento en una lista enlazada tiene una complejidad temporal de O(n) porque requiere recorrer la lista desde el principio hasta el elemento deseado. -->

5. **¿Qué estructura de datos usarías para implementar un sistema de deshacer/rehacer?**
    - A) Lista
    - B) Cola
    - C) Pila
    - D) Diccionario
    <!-- **Respuesta:** C
    **Justificación:** Una pila es adecuada para implementar un sistema de deshacer/rehacer porque permite agregar y quitar elementos del tope fácilmente. -->

6. **¿Qué operación no es posible directamente en una lista enlazada simple?**
    - A) Inserción en la cabeza
    - B) Eliminación del último elemento
    - C) Acceso al elemento en la posición N
    - D) Inserción después de un nodo dado
    <!-- **Respuesta:** C
    **Justificación:** Acceder a un elemento en una posición específica en una lista enlazada simple no es posible directamente y requiere recorrer la lista. -->

7. **¿Cuál es la principal diferencia entre una lista y una lista enlazada?**
    - A) Las listas permiten acceso aleatorio, mientras que las listas enlazadas no.
    - B) Las listas enlazadas son estáticas y las listas son dinámicas.
    - C) Las listas siempre están ordenadas y las listas enlazadas no.
    - D) Las listas enlazadas no pueden contener elementos duplicados.
    <!-- **Respuesta:** A
    **Justificación:** Las listas permiten acceso aleatorio a los elementos mediante índices, mientras que las listas enlazadas no permiten acceso directo y requieren recorrer los nodos. -->

8. **¿Qué método de `deque` se utiliza para eliminar y retornar el primer elemento?**
    - A) `pop()`
    - B) `remove()`
    - C) `popleft()`
    - D) `deletefirst()`
    <!-- **Respuesta:** C
    **Justificación:** El método `popleft()` de `deque` elimina y retorna el primer elemento. -->

9. **En una pila, ¿cuál es la complejidad temporal de la operación de agregar un elemento?**
    - A) O(1)
    - B) O(n)
    - C) O(log n)
    - D) O(n log n)
    <!-- **Respuesta:** A
    **Justificación:** Agregar un elemento a una pila tiene una complejidad temporal de O(1) porque se realiza en tiempo constante. -->

10. **¿Cuál es la mejor estructura de datos para implementar una lista de reproducción dinámica en un reproductor de música?**
    - A) Pila
    - B) Cola
    - C) Lista enlazada
    - D) Diccionario
    <!-- **Respuesta:** C
    **Justificación:** Una lista enlazada es adecuada para implementar una lista de reproducción dinámica porque permite inserciones y eliminaciones eficientes en cualquier posición. -->

---

### Cierre del Capítulo

Las estructuras de datos lineales son fundamentales en la informática debido a su simplicidad y eficiencia para diversas operaciones de manipulación de datos. Son las bases sobre las que se construyen estructuras de datos más complejas y algoritmos avanzados.

**Importancia de las Estructuras de Datos Lineales:**

1. **Eficiencia en la Gestión de Datos:**
   Las estructuras de datos lineales permiten una gestión eficiente de los datos en términos de tiempo y espacio. Por ejemplo, las listas permiten el acceso rápido a elementos mediante índices, mientras que las pilas y colas ofrecen operaciones eficientes de inserción y eliminación en los extremos.

2. **Simplicidad y Flexibilidad:**
   Estas estructuras son fáciles de entender e implementar, lo que las hace ideales para resolver problemas comunes en la programación. La flexibilidad de las listas para contener diferentes tipos de datos y la capacidad de las listas enlazadas para crecer dinámicamente son ejemplos de esta simplicidad y flexibilidad.

3. **Base para Estructuras y Algoritmos Complejos:**
   Las estructuras de datos lineales son la base sobre la cual se construyen estructuras de datos más complejas como árboles y grafos. Además, muchos algoritmos avanzados, como los algoritmos de búsqueda y ordenamiento, dependen de la comprensión y el uso eficiente de estas estructuras.

**Ejemplos de la Vida Cotidiana:**

1. **Listas:**
   - **Aplicaciones de Redes Sociales:** Las listas se utilizan para gestionar las publicaciones de un usuario, donde cada publicación es un elemento en la lista. Las operaciones como agregar una nueva publicación o eliminar una antigua son comunes.
   - **Sistemas de Gestión de Inventarios:** Las listas son útiles para almacenar productos y sus detalles en una tienda. Se pueden realizar operaciones como agregar nuevos productos, eliminar productos agotados y modificar detalles de productos existentes.

2. **Pilas:**
   - **Sistemas de Navegación Web:** Los navegadores web utilizan pilas para gestionar el historial de navegación. Cada vez que un usuario visita una nueva página, la URL se agrega a la pila. Al presionar el botón de "Atrás", la URL actual se elimina de la pila y se muestra la URL anterior.
   - **Editores de Texto:** Las pilas se utilizan para implementar la funcionalidad de deshacer/rehacer. Cada cambio en el documento se apila, permitiendo al usuario deshacer los cambios uno por uno.

3. **Colas:**
   - **Sistemas de Atención al Cliente:** En centros de llamadas, las colas gestionan las llamadas entrantes. La primera llamada en entrar es la primera en ser atendida, siguiendo el principio FIFO.
   - **Impresoras Compartidas:** En oficinas, las impresoras compartidas utilizan colas para gestionar los trabajos de impresión. Los trabajos se añaden a la cola y se procesan en el orden en que se reciben.

4. **Listas Enlazadas:**
   - **Sistemas de Gestión de Memoria:** Los sistemas operativos utilizan listas enlazadas para gestionar bloques de memoria libres y ocupados, permitiendo una gestión eficiente de la memoria.
   - **Aplicaciones de Música:** Las listas de reproducción en aplicaciones de música utilizan listas enlazadas para permitir la fácil inserción y eliminación de canciones en cualquier posición de la lista.

En resumen, las estructuras de datos lineales proporcionan una base sólida para el desarrollo de algoritmos eficientes y sistemas complejos. Su comprensión y uso adecuado son esenciales para cualquier programador que desee crear aplicaciones robustas y de alto rendimiento. El conocimiento de estas estructuras no solo mejora la capacidad de resolver problemas de programación, sino que también es fundamental para el diseño de software optimizado y escalable.



# 

### Capítulo 4: Estructuras de Datos No Lineales<a name="4"></a>

Las estructuras de datos no lineales permiten representar relaciones jerárquicas y redes complejas. Este capítulo cubre dos estructuras de datos no lineales fundamentales: árboles y grafos. Comprender estas estructuras y sus operaciones básicas es esencial para resolver problemas complejos de manera eficiente.

---

### Árboles

Un árbol es una estructura de datos jerárquica que consiste en nodos, donde cada nodo tiene un valor y referencias a nodos hijos. El nodo superior se llama raíz. Los nodos sin hijos se llaman hojas.

#### Definición y Operaciones Básicas

1. **Definición de un Nodo de Árbol:**
   ```python
   class Nodo:
       def __init__(self, valor):
           self.valor = valor
           self.izquierdo = None
           self.derecho = None
   ```

2. **Crear un Árbol Binario:**
   ```python
   class ArbolBinario:
       def __init__(self):
           self.raiz = None

       def agregar(self, valor):
           if self.raiz is None:
               self.raiz = Nodo(valor)
           else:
               self._agregar_recursivo(valor, self.raiz)

       def _agregar_recursivo(self, valor, nodo):
           if valor < nodo.valor:
               if nodo.izquierdo is None:
                   nodo.izquierdo = Nodo(valor)
               else:
                   self._agregar_recursivo(valor, nodo.izquierdo)
           else:
               if nodo.derecho es None:
                   nodo.derecho = Nodo(valor)
               else:
                   self._agregar_recursivo(valor, nodo.derecho)

       def en_orden(self):
           self._en_orden_recursivo(self.raiz)

       def _en_orden_recursivo(self, nodo):
           if nodo is not None:
               self._en_orden_recursivo(nodo.izquierdo)
               print(nodo.valor, end=' ')
               self._en_orden_recursivo(nodo.derecho)
   ```

#### Ejemplos de Uso

- **Árbol Binario de Búsqueda (BST):**
  ```python
  arbol = ArbolBinario()
  valores = [7, 3, 9, 1, 5, 8, 10]
  for v in valores:
      arbol.agregar(v)

  print("Recorrido en orden:")
  arbol.en_orden()
  ```

- **Árbol de Expresiones:**
  ```python
  class NodoExpresion:
      def __init__(self, valor):
          self.valor = valor
          self.izquierdo = None
          self.derecho = None

  raiz = NodoExpresion('+')
  raiz.izquierdo = NodoExpresion('*')
  raiz.derecho = NodoExpresion('3')
  raiz.izquierdo.izquierdo = NodoExpresion('2')
  raiz.izquierdo.derecho = NodoExpresion('1')

  def evaluar(nodo):
      if nodo.valor.isdigit():
          return int(nodo.valor)
      izquierda = evaluar(nodo.izquierdo)
      derecha = evaluar(nodo.derecho)
      if nodo.valor == '+':
          return izquierda + derecha
      elif nodo.valor == '*':
          return izquierda * derecha

  print("Resultado de la expresión:", evaluar(raiz))
  ```

---

### Grafos

Un grafo es una estructura de datos que consiste en un conjunto de nodos (o vértices) y un conjunto de aristas (o arcos) que conectan pares de nodos. Los grafos pueden ser dirigidos o no dirigidos.

#### Definición y Operaciones Básicas

1. **Definición de un Grafo:**
   ```python
   class Grafo:
       def __init__(self):
           self.vertices = {}

       def agregar_vertice(self, valor):
           if valor not in self.vertices:
               self.vertices[valor] = []

       def agregar_arista(self, desde, hacia):
           if desde in self.vertices and hacia in self.vertices:
               self.vertices[desde].append(hacia)
               self.vertices[hacia].append(desde)  # Quitar esta línea para grafos dirigidos
   ```

2. **Recorridos en Grafos:**
   ```python
   def bfs(grafo, inicio):
       visitados = set()
       cola = [inicio]
       while cola:
           vertice = cola.pop(0)
           if vertice not in visitados:
               visitados.add(vertice)
               print(vertice, end=' ')
               cola.extend([n for n in grafo.vertices[vertice] if n not in visitados])

   def dfs(grafo, inicio, visitados=None):
       if visitados is None:
           visitados = set()
       visitados.add(inicio)
       print(inicio, end=' ')
       for siguiente in grafo.vertices[inicio]:
           if siguiente not in visitados:
               dfs(grafo, siguiente, visitados)
   ```

#### Ejemplos de Uso

- **Grafo de Amistades:**
  ```python
  grafo_amistades = Grafo()
  amigos = ['A', 'B', 'C', 'D']
  for amigo in amigos:
      grafo_amistades.agregar_vertice(amigo)
  grafo_amistades.agregar_arista('A', 'B')
  grafo_amistades.agregar_arista('A', 'C')
  grafo_amistades.agregar_arista('B', 'D')
  grafo_amistades.agregar_arista('C', 'D')

  print("BFS:")
  bfs(grafo_amistades, 'A')

  print("\nDFS:")
  dfs(grafo_amistades, 'A')
  ```

- **Red de Computadoras:**
  ```python
  red_computadoras = Grafo()
  computadoras = ['PC1', 'PC2', 'PC3', 'PC4']
  for pc in computadoras:
      red_computadoras.agregar_vertice(pc)
  red_computadoras.agregar_arista('PC1', 'PC2')
  red_computadoras.agregar_arista('PC1', 'PC3')
  red_computadoras.agregar_arista('PC2', 'PC4')
  red_computadoras.agregar_arista('PC3', 'PC4')

  print("BFS:")
  bfs(red_computadoras, 'PC1')

  print("\nDFS:")
  dfs(red_computadoras, 'PC1')
  ```

---

### Ejercicios

1. **Crear un árbol binario y realizar un recorrido en orden.**
   ```python
   arbol = ArbolBinario()
   valores = [7, 3, 9, 1, 5, 8, 10]
   for v in valores:
       arbol.agregar(v)
   arbol.en_orden()
   ```

2. **Crear un árbol de expresión y evaluarlo.**
   ```python
   raiz = NodoExpresion('+')
   raiz.izquierdo = NodoExpresion('*')
   raiz.derecho = NodoExpresion('3')
   raiz.izquierdo.izquierdo = NodoExpresion('2')
   raiz.izquierdo.derecho = NodoExpresion('1')
   print("Resultado de la expresión:", evaluar(raiz))
   ```

3. **Crear un grafo y realizar un recorrido BFS.**
   ```python
   grafo = Grafo()
   vertices = ['A', 'B', 'C', 'D']
   for v in vertices:
       grafo.agregar_vertice(v)
   grafo.agregar_arista('A', 'B')
   grafo.agregar_arista('A', 'C')
   grafo.agregar_arista('B', 'D')
   grafo.agregar_arista('C', 'D')
   bfs(grafo, 'A')
   ```

4. **Crear un grafo y realizar un recorrido DFS.**
   ```python
   grafo = Grafo()
   vertices = ['A', 'B', 'C', 'D']
   for v in vertices:
       grafo.agregar_vertice(v)
   grafo.agregar_arista('A', 'B')
   grafo.agregar_arista('A', 'C')
   grafo.agregar_arista('B', 'D')
   grafo.agregar_arista('C', 'D')
   dfs(grafo, 'A')
   ```

5. **Crear un árbol binario de búsqueda y buscar un valor.**
   ```python
   class ArbolBinarioBusqueda(ArbolBinario):
       def buscar(self, valor):
           return self._buscar_recursivo(valor, self.raiz)

       def _buscar_recursivo(self, valor, nodo):
           if nodo is None or nodo.valor == valor:
               return nodo
           if valor < nodo.valor:
               return self._buscar_recursivo(valor, nodo.izquierdo)
           return self._buscar_recursivo(valor, nodo.derecho)

   arbol = ArbolBinarioBusqueda()
   valores = [7, 3, 9, 1, 5, 8, 10]
   for v in valores:
       arbol.agregar(v)
   resultado = arbol.buscar(5)
   print("Valor encontrado:", resultado.valor if resultado else "No encontrado")
   ```

6. **Agregar nodos

 a un árbol y contar el número de nodos.**
   ```python
   class ArbolConContador(ArbolBinario):
       def contar_nodos(self):
           return self._contar_nodos_recursivo(self.raiz)

       def _contar_nodos_recursivo(self, nodo):
           if nodo is None:
               return 0
           return 1 + self._contar_nodos_recursivo(nodo.izquierdo) + self._contar_nodos_recursivo(nodo.derecho)

   arbol = ArbolConContador()
   valores = [7, 3, 9, 1, 5, 8, 10]
   for v in valores:
       arbol.agregar(v)
   print("Número de nodos en el árbol:", arbol.contar_nodos())
   ```

7. **Determinar la altura de un árbol binario.**
   ```python
   class ArbolConAltura(ArbolBinario):
       def altura(self):
           return self._altura_recursiva(self.raiz)

       def _altura_recursiva(self, nodo):
           if nodo is None:
               return 0
           izquierda = self._altura_recursiva(nodo.izquierdo)
           derecha = self._altura_recursiva(nodo.derecho)
           return 1 + max(izquierda, derecha)

   arbol = ArbolConAltura()
   valores = [7, 3, 9, 1, 5, 8, 10]
   for v in valores:
       arbol.agregar(v)
   print("Altura del árbol:", arbol.altura())
   ```

8. **Implementar un grafo dirigido y realizar un recorrido DFS.**
   ```python
   class GrafoDirigido(Grafo):
       def agregar_arista(self, desde, hacia):
           if desde in self.vertices and hacia in self.vertices:
               self.vertices[desde].append(hacia)

   grafo = GrafoDirigido()
   vertices = ['A', 'B', 'C', 'D']
   for v in vertices:
       grafo.agregar_vertice(v)
   grafo.agregar_arista('A', 'B')
   grafo.agregar_arista('A', 'C')
   grafo.agregar_arista('B', 'D')
   grafo.agregar_arista('C', 'D')
   dfs(grafo, 'A')
   ```

9. **Encontrar el camino más corto en un grafo no dirigido utilizando BFS.**
   ```python
   from collections import deque

   def camino_mas_corto(grafo, inicio, fin):
       visitados = {inicio: None}
       cola = deque([inicio])
       while cola:
           actual = cola.popleft()
           if actual == fin:
               camino = []
               while actual is not None:
                   camino.append(actual)
                   actual = visitados[actual]
               return camino[::-1]
           for vecino in grafo.vertices[actual]:
               if vecino not in visitados:
                   visitados[vecino] = actual
                   cola.append(vecino)
       return None

   grafo = Grafo()
   vertices = ['A', 'B', 'C', 'D', 'E', 'F']
   for v in vertices:
       grafo.agregar_vertice(v)
   grafo.agregar_arista('A', 'B')
   grafo.agregar_arista('A', 'C')
   grafo.agregar_arista('B', 'D')
   grafo.agregar_arista('C', 'D')
   grafo.agregar_arista('C', 'E')
   grafo.agregar_arista('E', 'F')
   camino = camino_mas_corto(grafo, 'A', 'F')
   print("Camino más corto de A a F:", camino)
   ```

10. **Eliminar un nodo de un árbol binario.**
    ```python
    class ArbolBinarioEliminacion(ArbolBinario):
        def eliminar(self, valor):
            self.raiz = self._eliminar_recursivo(self.raiz, valor)

        def _eliminar_recursivo(self, nodo, valor):
            if nodo is None:
                return nodo
            if valor < nodo.valor:
                nodo.izquierdo = self._eliminar_recursivo(nodo.izquierdo, valor)
            elif valor > nodo.valor:
                nodo.derecho = self._eliminar_recursivo(nodo.derecho, valor)
            else:
                if nodo.izquierdo is None:
                    return nodo.derecho
                elif nodo.derecho is None:
                    return nodo.izquierdo
                temp = self._minimo_valor_nodo(nodo.derecho)
                nodo.valor = temp.valor
                nodo.derecho = self._eliminar_recursivo(nodo.derecho, temp.valor)
            return nodo

        def _minimo_valor_nodo(self, nodo):
            actual = nodo
            while actual.izquierdo is not None:
                actual = actual.izquierdo
            return actual

    arbol = ArbolBinarioEliminacion()
    valores = [7, 3, 9, 1, 5, 8, 10]
    for v in valores:
        arbol.agregar(v)
    arbol.eliminar(5)
    arbol.en_orden()
    ```

11. **Verificar si un grafo es conexo usando DFS.**
    ```python
    def es_conexo(grafo):
        visitados = set()
        dfs(grafo, list(grafo.vertices.keys())[0], visitados)
        return len(visitados) == len(grafo.vertices)

    grafo = Grafo()
    vertices = ['A', 'B', 'C', 'D']
    for v in vertices:
        grafo.agregar_vertice(v)
    grafo.agregar_arista('A', 'B')
    grafo.agregar_arista('A', 'C')
    grafo.agregar_arista('B', 'D')
    grafo.agregar_arista('C', 'D')
    print("El grafo es conexo:", es_conexo(grafo))
    ```

12. **Agregar pesos a las aristas de un grafo y mostrar los pesos.**
    ```python
    class GrafoPesado(Grafo):
        def agregar_arista(self, desde, hacia, peso):
            if desde in self.vertices and hacia in self.vertices:
                self.vertices[desde].append((hacia, peso))
                self.vertices[hacia].append((desde, peso))

    grafo = GrafoPesado()
    vertices = ['A', 'B', 'C', 'D']
    for v in vertices:
        grafo.agregar_vertice(v)
    grafo.agregar_arista('A', 'B', 1)
    grafo.agregar_arista('A', 'C', 2)
    grafo.agregar_arista('B', 'D', 3)
    grafo.agregar_arista('C', 'D', 4)

    for vertice in grafo.vertices:
        print(f"{vertice}: {grafo.vertices[vertice]}")
    ```

13. **Implementar el recorrido en postorden de un árbol binario.**
    ```python
    class ArbolPostorden(ArbolBinario):
        def postorden(self):
            self._postorden_recursivo(self.raiz)

        def _postorden_recursivo(self, nodo):
            if nodo is not None:
                self._postorden_recursivo(nodo.izquierdo)
                self._postorden_recursivo(nodo.derecho)
                print(nodo.valor, end=' ')

    arbol = ArbolPostorden()
    valores = [7, 3, 9, 1, 5, 8, 10]
    for v in valores:
        arbol.agregar(v)
    arbol.postorden()
    ```

14. **Encontrar el nodo de mayor valor en un árbol binario.**
    ```python
    class ArbolMayorValor(ArbolBinario):
        def mayor_valor(self):
            return self._mayor_valor_recursivo(self.raiz)

        def _mayor_valor_recursivo(self, nodo):
            if nodo is None:
                return float('-inf')
            izquierdo = self._mayor_valor_recursivo(nodo.izquierdo)
            derecho = self._mayor_valor_recursivo(nodo.derecho)
            return max(nodo.valor, izquierdo, derecho)

    arbol = ArbolMayorValor()
    valores = [7, 3, 9, 1, 5, 8, 10]
    for v in valores:
        arbol.agregar(v)
    print("Mayor valor en el árbol:", arbol.mayor_valor())
    ```

15. **Implementar una función para detectar ciclos en un grafo.**
    ```python
    def detectar_ciclo(grafo):
        visitados = set()

        def dfs_ciclo(vertice, padre):
            visitados.add(vertice)
            for vecino in grafo.vertices[vertice]:
                if vecino not in visitados:
                    if dfs_ciclo(vecino, vertice):
                        return True
                elif vecino != padre:
                    return True
            return False

        for vertice in grafo.vertices:
            if vertice not in visitados:
                if dfs_ciclo(vertice, None):
                    return True
        return False

    grafo = Grafo()
    vertices =

 ['A', 'B', 'C', 'D']
    for v in vertices:
        grafo.agregar_vertice(v)
    grafo.agregar_arista('A', 'B')
    grafo.agregar_arista('A', 'C')
    grafo.agregar_arista('B', 'D')
    grafo.agregar_arista('C', 'D')
    print("El grafo tiene ciclo:", detectar_ciclo(grafo))
    ```

---

### Examen: Estructuras de Datos No Lineales

1. **¿Qué estructura de datos se utiliza para representar relaciones jerárquicas?**
    - A) Lista
    - B) Pila
    - C) Árbol
    - D) Cola
 
     **Respuesta:** C
    **Justificación:** Un árbol es una estructura de datos jerárquica que se utiliza para representar relaciones jerárquicas. 

2. **¿Cuál es el recorrido en orden de un árbol binario con los nodos [2, 1, 3]?**
    - A) 1, 2, 3
    - B) 2, 1, 3
    - C) 2, 3, 1
    - D) 1, 3, 2

     **Respuesta:** A
    **Justificación:** El recorrido en orden de un árbol binario visita los nodos en el orden: izquierda, raíz, derecha. 

3. **¿Qué estructura de datos se utiliza para representar redes complejas y relaciones?**
    - A) Lista
    - B) Grafo
    - C) Árbol
    - D) Cola
 
     **Respuesta:** B
    **Justificación:** Un grafo es una estructura de datos que se utiliza para representar redes complejas y relaciones entre nodos. 

4. **En un grafo no dirigido, ¿cómo se representa una conexión entre dos nodos?**
    - A) Mediante una arista que apunta de un nodo a otro
    - B) Mediante un nodo adicional
    - C) Mediante una arista bidireccional
    - D) Mediante un bucle
 
     **Respuesta:** C
    **Justificación:** En un grafo no dirigido, una conexión entre dos nodos se representa mediante una arista bidireccional. 

5. **¿Cuál es la complejidad temporal de insertar un valor en un árbol binario de búsqueda balanceado?**
    - A) O(1)
    - B) O(log n)
    - C) O(n)
    - D) O(n log n)
 
     **Respuesta:** B
    **Justificación:** Insertar un valor en un árbol binario de búsqueda balanceado tiene una complejidad temporal de O(log n) en promedio. 

6. **¿Qué tipo de recorrido de un árbol binario visita primero la raíz, luego el subárbol izquierdo y finalmente el subárbol derecho?**
    - A) Recorrido en orden
    - B) Recorrido en preorden
    - C) Recorrido en postorden
    - D) Recorrido en nivel
  
     **Respuesta:** B
    **Justificación:** En el recorrido en preorden, se visita primero la raíz, luego el subárbol izquierdo y finalmente el subárbol derecho. 

7. **¿Cuál es la diferencia principal entre un grafo dirigido y un grafo no dirigido?**
    - A) La cantidad de nodos
    - B) La dirección de las aristas
    - C) El peso de las aristas
    - D) La presencia de ciclos
  
     **Respuesta:** B
    **Justificación:** En un grafo dirigido, las aristas tienen una dirección, mientras que en un grafo no dirigido, las aristas no tienen dirección. 

8. **¿Qué estructura de datos se usa para realizar una búsqueda en amplitud (BFS) en un grafo?**
    - A) Pila
    - B) Cola
    - C) Lista
    - D) Árbol
  
    **Respuesta:** B -->
    **Justificación:** Para realizar una búsqueda en amplitud (BFS) en un grafo se utiliza una cola.

9. **¿Qué método se utiliza para agregar un nodo a un árbol binario de búsqueda en Python?**
    - A) add()
    - B) append()
    - C) insert()
    - D) agregar()
  
   **Respuesta:** D
    **Justificación:** El método `agregar()` se utiliza comúnmente para insertar un nodo en un árbol binario de búsqueda en Python.

10. **¿Cuál es la principal aplicación de los grafos en las redes sociales?**
    - A) Representar relaciones jerárquicas
    - B) Representar conexiones de amistad
    - C) Representar tareas pendientes
    - D) Representar historial de navegación
   
    **Respuesta:** B
    **Justificación:** Los grafos en las redes sociales se utilizan principalmente para representar conexiones de amistad entre usuarios.

11. **¿Qué algoritmo se utiliza para encontrar el camino más corto en un grafo ponderado?**
    - A) Algoritmo de Dijkstra
    - B) Algoritmo DFS
    - C) Algoritmo BFS
    - D) Algoritmo de Kruskal
  
     **Respuesta:** A
    **Justificación:** El algoritmo de Dijkstra se utiliza para encontrar el camino más corto en un grafo ponderado. 

12. **¿Cuál es la complejidad temporal de recorrer un árbol binario en orden?**
    - A) O(1)
    - B) O(log n)
    - C) O(n)
    - D) O(n log n)
   
    **Respuesta:** C
    **Justificación:** Recorrer un árbol binario en orden tiene una complejidad temporal de O(n) porque cada nodo se visita una vez.

13. **¿Qué estructura de datos es más adecuada para implementar un árbol de expresión?**
    - A) Lista
    - B) Pila
    - C) Árbol
    - D) Cola
   
    **Respuesta:** C
    **Justificación:** Un árbol es más adecuado para implementar un árbol de expresión, donde cada nodo representa un operador o un operando.

14. **¿Qué estructura de datos es más adecuada para detectar ciclos en un grafo?**
    - A) Lista
    - B) Pila
    - C) Árbol
    - D) Grafo
   
    **Respuesta:** D    
    **Justificación:** Un grafo es adecuado para detectar ciclos, y se pueden usar técnicas como DFS para la detección de ciclos.

15. **¿Cuál es la principal ventaja de usar un árbol binario de búsqueda (BST)?**
    - A) Inserción rápida
    - B) Búsqueda eficiente
    - C) Ordenamiento automático de elementos
    - D) Todas las anteriores
    **Respuesta:** D
    
    **Justificación:** Un árbol binario de búsqueda (BST) ofrece inserción rápida, búsqueda eficiente y mantiene los elementos ordenados automáticamente.

---

### Cierre del Capítulo

Las estructuras de datos no lineales son fundamentales para resolver problemas complejos que requieren la representación de relaciones jerárquicas y redes. Comprender y utilizar adecuadamente árboles y grafos es esencial para cualquier programador que desee crear aplicaciones eficientes y escalables.

**Importancia de las Estructuras de Datos No Lineales:**

1. **Representación de Relaciones Complejas:**
   Las estructuras de datos no lineales permiten representar relaciones complejas entre elementos. Por ejemplo, los árboles se utilizan para representar jerarquías y los grafos para representar redes.

2. **Eficiencia en Algoritmos Complejos:**
   Muchos algoritmos avanzados, como los de búsqueda y optimización, se basan en árboles y grafos. Estos algoritmos son fundamentales para aplicaciones que requieren eficiencia y rapidez.

3. **Aplicaciones Diversas:**
   Las estructuras de datos no lineales tienen aplicaciones en una amplia variedad de campos, desde la biología computacional hasta las redes sociales y la inteligencia artificial. Por ejemplo, los árboles se utilizan en la construcción de parsers en compiladores y los grafos en la representación de redes de transporte.

**Ejemplos de la Vida Cotidiana:**

1. **Árboles:**
   - **Sistemas de Archivos:** Los sistemas de archivos de las computadoras se representan como árboles, donde las carpetas son nodos que contienen archivos y otras carpetas.
   - **Jerarquías Organizacionales:** Las estructuras organizacionales de las empresas a menudo se representan como árboles, con un director general en la raíz y otros empleados en niveles inferiores.

2. **Grafos:**
   - **Redes Sociales:** Las redes sociales utilizan grafos para representar las conexiones entre usuarios. Cada usuario es un nodo y cada amistad es una arista.
   - **Sistemas de Transporte:** Las rutas de autobuses y trenes se representan como grafos, donde las estaciones son nodos y las rutas son aristas.

En resumen, las estructuras de datos no lineales son herramientas poderosas que permiten a los programadores representar y manipular datos complejos de manera eficiente. Su comprensión y uso adecuado son esenciales para el desarrollo de aplicaciones robustas y escalables, mejorando significativamente la capacidad de resolver problemas complejos en diversos campos.

# 




# 
