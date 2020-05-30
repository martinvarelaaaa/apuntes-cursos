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


