# POO and Algorithms with Python

Los objetivos de estos apuntes son:

- Entender como funciona la Programación Orientada a Objetos
- Entender como medir eficiencia temporal y espacial de los algoritmos
- Entender cómo y por qué graficar
- Aprender a resolver problemas de búsqueda, ordenación y optimización

[Repositorio de código utilizado](https://github.com/martinvarelaaaa/python-notes).

Los apuntes son de cuando realice [el siguiente curso](https://platzi.com/clases/poo-python/).

## Programación orientada a objetos en Python

Uno de los elementos más importantes de los lenguajes de programación
es la utilización de clases para organizar programas en módulos y abstracciones
de datos.

La clave para entender la programación orientada a objetos es pensar en objetos
como agrupaciones de datos y los métodos que operan en dichos datos.

Por ejemplo, podemos representar a una persona con propiedades como nombre,
edad, género, etc. y los comportamientos de dicha persona como caminar, cantar,
comer, etc. De la misma manera podemos representar unos audífonos con propiedades
como su marca, tamaño, color, etc. y sus comportamientos como reproducir música,
pausar y avanzar a la siguiente canción.

### Clases en Python

Las clases nos permiten crear nuevos tipos que contiene información arbitraria
sobre un objeto. En el caso del hotel, podríamos crear dos clases Hotel() y
Cuarto() que nos permitiera dar seguimiento a las propiedades como número de
cuartos, ocupación, aseo, tipo de habitación, etc.

Es importante resaltar que las clases sólo proveen estructura. Son un molde con
el cual podemos construir objetos específicos. La clase señala las propiedades
que los hoteles que modelemos tendrán, pero no es ningún hotel específico. Para
eso necesitamos las instancias.

### Instancias en Python

Mientras que las clases proveen la estructura, las instancias son los objetos
reales que creamos en nuestro programa: un hotel llamado Hilton.

Otra forma de pensarlo es que las clases son como un formulario y una vez que
se llena cada copia del formulario tenemos las instancias que pertenecen a
dicha clase. Cada copia puede tener datos distintos, al igual que cada instancia
es distinta de las demás (aunque todas pertenecen a una misma clase).

```py
class Hotel:
    pass
```

Para crear la instancia:

```py
hotel = Hotel()
```

#### Atributos de la instancia

Todas las clases crean objetos y todos los objetos tienen atributos. Utilizamos
el método especial **init** para definir el estado inicial de nuestra instancia.
Recibe como primer parámetro obligatorio self (que es simplemente una
referencia a la instancia).

```py
class Hotel:

    def __init__(self, numero_maximo_de_huespedes, lugares_de_estacionamiento):
        self.numero_maximo_de_huespedes = numero_maximo_de_huespedes
        self.lugares_de_estacionamiento = lugares_de_estacionamiento
        self.huespedes = 0


hotel = Hotel(numero_maximo_de_huespedes=50, lugares_de_estacionamiento=20)
print(hotel.lugares_de_estacionamiento) # 20
```

#### Métodos de instancia

Mientras que los atributos de la instancia describen lo que representa el
objeto, los métodos de instancia nos indican qué podemos hacer con las
instancias de dicha clase y normalmente operan en los mencionados atributos.

Los métodos son equivalentes a funciones dentro de la definición de la clase,
pero todos reciben self como primer argumento.

```py
class Hotel:

    def anadir_huespedes(self, cantidad_de_huespedes):
        self.huespedes += cantidad_de_huespedes

    def checkout(self, cantidad_de_huespedes):
        self.huespedes -= cantidad_de_huespedes

    def ocupacion_total(self):
        return self.huespedes


hotel = Hotel(50, 20)
hotel.anadir_huespedes(3)
hotel.checkout(1)
hotel.ocupacion_total() # 2
```

## Tipos de datos abrstractos, clases e instancias

En Python todo es un objeto y tiene un tipo. Las formas de interacturar con objetos son:

- Creación
- Manipulación
- Destrucción

Ventajas de utilizar estos objetos:

- Descomposición
- Abstracción
- Encapsulación

### Instancias

Mientras que la clase es un molde, a los objetos también se los conoce como instancia. Cuando se crea una instancia, se ejecuta el método `__init__` de la clase. Todos los métodos de una clase reciben el parámetro `self`.

La convención para definir una variable privada en Python es que el nombre comience con `_`.

### Descomposición

La descomposición es partir un problema en problemas más chicos. Las clases permiten crear mayores abstracciones en forma de componentes. Cada clase se encarga de una parte del problema y el programa se vuelve más fácil de mantener.

Por ej un auto, funciona por descomposición. La rueda resuelva un problema, la puerta otro, la caja de cambios otro, etc.

### Abstracción

La abstracción permite enfocarnos en la información relevante. Separar la información central de los detalles secundarios. Podemos visualizar variables y métodos(privados y públicos).

### Encapsulación

La encapsulación permite agrupar datos y su comportamiento en un solo lugar. Controla el acceso a los datos y previene las modificaciones no autorizadas.

La programación defensiva se basa en este concepto de encapsulación, para detminar cuando y como se modifica una clase, y cuando y como se permiten leer los datos de la clase.

### Herencia

La herencia permite modelar una jerarquia de objetos. Permite compartir cierto comportamiento entre cada uno de estos objetos. Esto ayuda a tener el código más organizado construyendo jerarquias que tengan sentido.

Al padre se lo conoce como superclase y al hijo con superclase.

### Polimorfismo

El polimorfismo es la habilidad que tiene un objeto de tomar varias formas. En Python, nos permite cambiar el comportamiento de una superclase para adaptarlo a la subclase.

Simplemente se pisa el método de la superclase en la subclase.

## Complejidad algorítmica

Nos permite comparar la eficiencia entre dos algoritmos diferentes, esto nos permite predecir el tiempo que se va a tardar en resolver un problema.

### Complejidad temporal vs complejidad espacial

La complejidad puede ser temporal si medimos cuanto tiempo demora en ejecutarse, sino que también de forma espacial, es decir, cuando espacio en memoria ocupa la ejecución de ese algorítmo.

Podemos definir la complejidad algorítmica como **T(n)**.

### Aproximaciones

¿Cómo se podría implementar la función T?

- Cronometrar el tiempo en el que corre un algoritmo
- Contar los pasos con una medida abstracta de operación
- **Contar los pasos conforme nos aproximamos al infinito**

El problema de estas técincas es que las soluciones pueden variar dependiendo de la máquina en la que estemos o de la lógica misma del algoritmo. La forma de contar pasos conforme nos aproximamos al infinito es la mejor manera.

### Conteo abstracto de operación

Medir la eificnecia de los algoritmos en base al tiempo que demoran en ejecutarse no sirve, porque va a depender mucho de la maquina en dónde se ejecute o por ejemplo de la cantidad de datos que deberá resolver, por lo tanto, es una métrica muy inestable.

El conteo de los pasos que ejecuta un algoritmo es mucho más efectivo.

### Notación asintótica

El crecimiento asintótico es un crecimiento que tiende al infinito. Algunos puntos sobre este enfoque para medir la eficiencia de un algoritmo:

- No importan las varciaciones pequeñas
- El enfoque se centra en lo que pasa conforme al tamaño del problema se acerca al infinito
- Mejor de los casos, promedio, pero de los casos
- Big O
- Nada mas importa el termino de mayor tamaño

¿Cómo dedir el Big O?

```python
def f(n):
    for i in range(n):
        print(i)

    for i in range(n):
        print(i)

# O(n) + O(n) = O(n + n) = O(2n) = O(n)
```

Esta función tiene un crecimiento lineal ya que depende de `n` cuando crece.

```python
def f(n):
    for i in range(n):
        print(i)

    for i in range(n * n):
        print(i)

# O(n) + O(n * n) = O(n + n2) = O(n2)
```

Esta función crece de forma cuadratica.

```python
def fibonacci(n):
    if n == 0 or n ==1:
        return 1

    return fibonacci(n - 1) + fibonacci(n - 1)

# O(2**n)
```

Esta es una función de tipo recursividad múltiple. Es un crecimiento exponencial.

### Clases de complejidad algoritmica

- O(1) Constante
- O(n) Lineal
- O(log n) Logaritmica
- O(n log n) Log lineal
- O(n**2) Polinominal
- O(2**n) Exponencial

## Algoritmos de búsqueda y ordenación

### Búsqueda lineal

Busca en todos los elementos de manera secuencial.

¿Cuál es el peor caso? `O(n)`.

```python
def lineal_search(list, objective):
    match = False

    for element in list:
        if element == objective:
            match = True
            break
    return match
```

### Búsqueda binaria

Se basa en la estrategia divide y conquista. El problema se divide en 2 en cada iteración hasta resolverlo. Este algoritmo asume que la lista esta ordenada.

¿Cuál es el peor caso? ``.

```python
def binary_search(list, start, end, objective):
    if start > end:
        return False

    middle = (start + end) // 2

    if list[middle] == objective:
        return True
    elif list[middle] < objective:
        return binary_search(list, middle + 1, end, objective)
    elif list[middle] > objective:
        return binary_search(list, start, middle - 1, objective)
```