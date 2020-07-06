# Open Source (OSS)

Estos son los apuntes sobre que es Open Source, algunos ejemplos de proyectos Open Source, sus fundamentos filósificos y como se hace para colaborar en un proyecto (o crear uno propio).

## ¿Qué es?

Originalmente, la expresión open source (o código abierto) hacía referencia al software open source (OSS). El software open source es un código diseñado de manera que sea accesible al público: todos pueden ver, modificar y distribuir el código de la forma que consideren conveniente. El software open source se desarrolla de manera descentralizada y colaborativa, así que depende de la revisión entre compañeros y la producción de la comunidad. Además, suele ser más económico, flexible y duradero que sus alternativas propietarias, ya que las encargadas de su desarrollo son las comunidades y no un solo autor o una sola empresa.

El open source se convirtió en un movimiento y una forma de trabajo que trasciende la producción del software. Este movimiento utiliza los valores y el modelo de producción descentralizada del software open source para hallar nuevas maneras de solucionar problemas en las comunidades y los sectores.

[Fuente Red Hat.](https://www.redhat.com/es/topics/open-source/what-is-open-source)

## Historia del Software Libre y el Open Source

La historia del open source va de la mano con la historia de Internet. En las décadas de 1950 y 1960, los investigadores que desarrollaron las primeras tecnologías de Internet y los protocolos de redes de telecomunicaciones dependían de un entorno de investigación colaborativo y abierto.

El software comenzó siendo libre, en la década de los 60, nadie lo veia como un negocio, simplemente se compartia. Al avanzar la decada y sobre los 70 las empresas empezaron a tener cada vez mas demanda de los usuarios y errores a corregir, entonces se empezaron a dar cuenta que el software se podia vender, ahí todo cambio, empezaron a ponerle marca registrada al software y a evitar que se compartiera entre personas de forma libre.

Hubo un punto de inflexión que fue una carta que publicó Bill Gates, en 1976, llamada [“Carta abierta a los aficionados”](https://es.wikipedia.org/wiki/Carta_abierta_a_los_aficionados#:~:text=La%20%C2%ABCarta%20abierta%20a%20los,ante%20la%20creciente%20pirater%C3%ADa%20de) donde decía que todos los aficionados al software libre eran unos ladrones. En la carta, Gates expresó su frustración con la mayoría de aficionados a las computadoras que usaban el software Altair BASIC de su compañía sin haberlo pagado. Afirmó que tal copia no autorizada generalizada desalentaba en efecto a los desarrolladores a invertir tiempo y dinero en la creación de software de alta calidad. Citó la injusticia de obtener los beneficios del tiempo, el esfuerzo y el capital de los autores de software sin pagarlos.

### Software Libre vs Open Source

Durante muchos años, el software open source se conoció con el nombre de "software libre".

#### Software Libre

En 1983, Richard Stallman estableció oficialmente el movimiento del software libre en el Proyecto GNU. El movimiento del software libre se organizó en torno a la idea de la libertad del usuario:

1. La libertad de usar el programa con cualquier proposito
2. La libertad de estudiar como funciona el programa 
3. La libertad de poder distribuir copias
4. La libertad de mejorar el programa y hacer públicas esas mejoras a los demás

**El software libre es la contraparte del software propietario o de "código cerrado".** El software de código cerrado está altamente protegido. Solo los propietarios del código fuente tienen el derecho legal de acceder a él. La modificación o la copia del código fuente cerrado están prohibidas por ley, y el usuario solo paga por el uso del software tal y como está; no puede modificarlo para usos nuevos ni compartirlo con la comunidad.

**Sin embargo, la denominación "software libre" ha generado mucha confusión. El software libre no implica necesariamente que sea gratuito, sino que los usuarios pueden utilizarlo como lo deseen.** La comunidad ha intentado explicar que el término "libre" hace referencia a la libertad y no significa "libre de costo".

#### Open Source

Eric Raymond, un personaje bastante polémico para la época, publicó en 1997, un ensayo sumamente influyente llamado ["La catedral y el bazar"](https://es.wikipedia.org/wiki/La_catedral_y_el_bazar). Eric quería que el mundo supiera que el software era mejor cuando se compartía, es decir, cuando era colaborativo, abierto y modificable; que se le podían dar usos nuevos y mejores, que era más flexible, más económico y que contaba con mayor durabilidad sin depender de un proveedor.

En 1998 la empresa NetScape implementó la tecnología open source en su proyecto Mozilla y lanzó el código fuente como software libre. Posteriormente, ese código open source se convirtió en la base para Mozilla Firefox y Mozilla Thunderbird.

El hecho de que Netscape respaldara el software open source supuso una presión para el resto de la comunidad y las empresas de tecnología. Los beneficios que tuvo NetScape motivaron a que de a poco más y más empresas se sumaran a esta ola.

A principios de 1998, se fundó la Open Source Initiative, lo cual formalizó la expresión "open source" y estableció una definición común en todo el sector. Esta organización hacia foco sobre los beneficios comerciales que traía desarrollar código open source.

El principal actor que apoyó a este movimiento fue [Linus Torvalds](https://es.wikipedia.org/wiki/Linus_Torvalds), creador de Linux y de Git, entre otras cosas.

10 máximas del código open source:

1. Libre redistribución: el software debe poder ser regalado o vendido libremente
2. Código fuente: el código fuente debe estar incluido u obtenerse libremente
3. Trabajos derivados: la redistribución de modificaciones debe estar permitida
4. Integridad del código fuente del autor: las licencias pueden requerir que las modificaciones sean redistribuidas solo como parches
5. La licencia no debe discriminar a ninguna persona o grupo: nadie puede dejarse fuera
6. Sin discriminación de áreas de iniciativa: los usuarios comerciales no pueden ser excluidos
7. Distribución de la licencia: deben aplicarse los mismos derechos a todo el que reciba el programa
8. La licencia no debe ser específica de un producto: el programa no puede licenciarse solo como parte de una distribución mayor
9. La licencia no debe restringir otro software: la licencia no puede obligar a que algún otro software que sea distribuido con el software abierto deba también ser de código abierto
10. La licencia debe ser tecnológicamente neutral: no debe requerirse la aceptación de la licencia por medio de un acceso por clic de ratón o de otra forma específica del medio de soporte del software

Estos puntos son más prácticos que ideológicos, a diferencia de las 4 libertades del software libre. Asi y todo es compatible con las 4 máximas del software libre.

#### Conslusión

El software libre se centra más en aspectos ideológicos o éticos y tiende a ser más estricto. De hecho cualquier software libre es también open source. Pero esto no pasa al contrario, por ejemplo, Ubuntu es Open Source pero no software libre, porque incluye la instalación de otros programas y además contiene algunos programas comerciales dentro.

La diferencia principal la vemos en como cada organización ve el software. El software libre no permite que a traves de este se puedan instalar otros softwares comerciales, el open source si.

#### ¿Cuál es mejor?

Yo opino que Open Source es más práctico, el Software Libre es más una utopia, ya que no me deja por ejemplo instalar encima un software no libre.

## Proyectos Open Source

Acá un listado de proyectos Open Source que utilizamos todo el tiempo:

- WordPress
- PHP
- Android
- Linux
- Torrent
- La base del sistema operativo de iPhone
- Chrome
- Visual Studio Code
- Disscord
- Bootstrap
- NodeJs
- ReactJs

[Explorar proyectos Open Source en Github.](https://github.com/explore)

## Links

[Free software, free society: Richard Stallman](https://www.youtube.com/watch?v=Ag1AKIl_2GM)

[What the Tech Industry Has Learned from Linus Torvalds](https://www.youtube.com/watch?v=7XTHdcmjenI)

[Haz tu primera contribución Open Source](https://www.youtube.com/watch?v=KUVpaY-MYUc)