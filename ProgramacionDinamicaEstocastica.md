# Programaión dinámica y estocástica

Es uno de los conceptos más difíciles de digerir dentro del mundo de la ciencia de la computación.

## Programación dinámica

Es una de las técnicas más poderosas para optimizar ciertos tipos de problemas.

### Subestructura optima

Una solución global óptima se puede encontrar al combinar soluciones óptimas de subproblemas locales.

### Problemas empalmados

Una solución óptima que involucra resolver el mismo problema en varias ocasiones.

## Memoization

- La memorización es una técnica para guardar computos previos y evitar realizarlos nuevamente.

- Normalmente se utiliza un diccionario, donde las consultas se pueden hacer en O(1).

- Intercambia tiempo por esapcio.

[Fibonacci con prog dinamica y memoization.](https://github.com/martinvarelaaaa/python-notes/blob/master/prog_dinamica.py) Se explican los beneficios de cambiar tiempo por espacio. Es importante que sean problemas empalmados como el caso de fibonacci, porque sino no podemos ir guardando en el codigo el resultado de cada computo, o en realidad si, pero no tendria utilidad ni sentido.