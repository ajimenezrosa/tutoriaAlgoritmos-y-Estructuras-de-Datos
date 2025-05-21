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
    - **Pregunta:** Enumera los tipos de datos básicos en Python y proporciona un ejemplo de cada uno.
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

# 




### Capítulo 3: Estructuras de Datos Lineales

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