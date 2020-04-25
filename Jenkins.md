# Jenkins

[Jenkins](https://jenkins.io/) es un servidor de automatización open source escrito en Java. Está basado en el proyecto Hudson y es, dependiendo de la visión, un fork del proyecto o simplemente un cambio de nombre.

_Definición de Wikipedia._

## Introducción

Jenkins ayuda en la automatización de parte del proceso de desarrollo de software mediante integración continua y facilita ciertos aspectos de la entrega continua. Admite herramientas de control de versiones como CVS, Subversion, Git, Mercurial, Perforce y Clearcase y puede ejecutar proyectos basados en Apache Ant y Apache Maven, así como secuencias de comandos de consola y programas por lotes de Windows. El desarrollador principal es Kohsuke Kawaguchi. Publicado bajo licencia MIT, Jenkins es software libre.

- Se puede correr en Linux, Windows y Mac.
- Es muy extensible gracias a su sistema de plugins.
- Tiene una comunidad muy grande que ha desarrollado muchos plugins
- Hay muchas personas de la comunidad respondiendo consultas y ayudando a resolver problemas.
- Permite escalar de manera y vertical, puede ejecutar muchos trabajos recurrentemente, dandole recursos a medida que mas procesos tenga que correr. Eventualmente, se puede escalar horizontalmente gracias a los slaves.
- Es muy activo en cuanto a actualizaciones, mejoras y nuevas features.
- Se pueden escribir los jobs de Jenkins en código, eso permite programar la automatización, eso ayuda a poder llevar ese código a diferentes Jenkins. La famosa infrastructura cómo código.

## Instalación y configuración

Jenkins tiene guías de instalación para todos los sistemas oprativos. En este caso lo voy a instalar utilizando una imagen de [Docker](https://www.docker.com/).

Primero crear una red de Docker:

```bash
docker network create jenkins
```

Crear los siguientes volumenes.

```bash
docker volume create jenkins-docker-certs
docker volume create jenkins-data
```

Para poder ejecutar comandos Docker dentro de los nodos de Jenkins:

```bash
docker container run \
  --name jenkins-docker \
  --rm \
  --detach \
  --privileged \
  --network jenkins \
  --network-alias docker \
  --env DOCKER_TLS_CERTDIR=/certs \
  --volume jenkins-docker-certs:/certs/client \
  --volume jenkins-data:/var/jenkins_home \
  --publish 2376:2376 \
  docker:dind
```

Descargar la imagen de Jenkins y correrla en un contenedor:

```bash
docker container run \
  --name jenkins-blueocean \
  --rm \
  --detach \
  --network jenkins \
  --env DOCKER_HOST=tcp://docker:2376 \
  --env DOCKER_CERT_PATH=/certs/client \
  --env DOCKER_TLS_VERIFY=1 \
  --publish 8080:8080 \
  --publish 50000:50000 \
  --volume jenkins-data:/var/jenkins_home \
  --volume jenkins-docker-certs:/certs/client:ro \
  jenkinsci/blueocean
```

Ir a [localhost:8080](http://localhost:8080) y seguir la guía de configuración.

Para ver la contraseña que hay que ingresar en el wizard de setup, ver los logs del container:

```bash
docker logs jenkins-blueocean
```

Instalar los plugins sugeridos por Jenkins y crear los usuarios administradores.

## Manejo de usuarios

Jenkis tiene muchas formas de manejar usuarios, pero la que viene por defecto es la de dejar que Jenkins maneje los usuarios.

Es importante configurar bien los usuarios ya que estarán trabajndo sobre la insfractuctura. Por temas de privilegios, auditorias, etc.

Ir a: `Manage Jenkins / Manage Users / Create User`

Allí podrás crear un usuario y administrar sus privilegios.

## ¿Qué es un Job?

Es la unidad mas importante de Jenkins.

Ir a `Create a new Job` y crear un primer Job:

- Ponle un nombre
- Selecciona un tipo, en este caso `Freestyle project`
- Ir al tab `Build Enviroment`
- Ir a la opción `Build` y seleccionar el valor `Execute Shell`
- Escribir el comando `echo "Hola Mundo"`
- Hacer click en `Build now`

En el historial de tareas tiene que aparecer una nueva con el nombre #1, hacer click ahi y se podrá ver la consola con la ejecución del `echo`.

```
+ echo 'Hola Mundo'
Hola Mundo
Finished: SUCCESS
```

Poder separar las ejecuciones de las tareas en diferentes jobs permite poder auditar todo lo que pasa en la insfractuctura de forma separada, eso es una gran herramienta para encontrar fallas o mejoras.

## Configuración de un Job

Hasta ahora creamos un job y vimos como ejecutarlo a mano. Pero generalmente vamos a querer automatizar la ejecución, esto se hace con la configuración.

- Ingresar en el Job
- Ir a la configuración

Se pueden configurar cosas como: descripción del Job, descartar el Job luego de ejecutarse, projecto de GitHub, pasarle parámetros, deshabilitar el Job, fuentes de código, configurar los Triggers, build enviroment, etc.

Es una buena práctica marcar la casilla `Delete workspace before builds starts` para que se limpien los directorios antes de cada ejecución. Otra es configurar que se aborte el Job si falla por más de x minútos.

Si por ejemplo configuramos una parámetro de entrada al Job, con una variable `NAME`, el comando que teníamos anteriormente se podría ejecutar así:

```
echo "Hello Word $NAME"
```

Para ejecutarlo, ir a `Build with parameters`.

También se pueden configurar `Post-build Actions`, esto permite por ejemplo, que cuando termine un Job, se envíe en mail, se haga un push en Github, etc.

Hay un post-action build muy interesante que es el `Archive the artifacts`, sirve para interactuar con otros Jobs y hacer pipelines.

## ¿Cómo Jenkins interactúa con su máquina local?

Se puede hacer más que ejecutar un `echo`, para eso, por ejemplo podemos interactuar con la maquina.

Como ya mencione, Jenkins permite ejecutar Node, Python, etc. Pero Jenkins, esta escrito en Java, ¿entonces como hace?

Por ejemplo en lugar de ejecutar el `echo` se podría ejecutar Node.

```
echo "Hello Word $NAME"
node
```

Luego de ejecutar el Job, este da error, porque Jenkins no encuentra Node. Eso es porque en la maquina en dónde se esta ejecutando Jenkins, Node no está instalado.

Para solucionarlo, hay que ir a los plugins de Jenkis, [buscar el de Nodejs e instalarlo](https://plugins.jenkins.io/nodejs/), luego de instalarlo en la configuración se pueden configurar versiones y algunas cosas más.

Ahora al ejecutar el Job nuevamente, funciona.

## Los Plugins de Jenkins

Como ya se hizo en el paso anterior, en Jenkins existen Plugins que se pueden instalar para facilitarnos la vida.

Los plugins son módulos que extienden a Jenkis, hay para hacer casi cualquier cosa.

## Conectar Jenkis a Github

Se puede conectar un Job directamente con un repositorio de Github. Para eso hay que crear un Job freestyle y en la configuración conectar un repositorio de Github.

Luego se puede agregar un trigger que se ejecute cuando se haga push a los branchs que le digamos. Por ejemplo se podría configurar para que se ejecuten test o se haga un build.

Para que los triggers funcionen, hay que instalar el plugin de Github y agregar el webhook en el repositorio de Github.

## Pipelines

Permiten configurar los Jobs a traves de código. Existen dos formas de implementarlos: `scripts pipeline` y `declarative pipelines`. 

El Pipeline declarativo nos permite configurar todo a traves de código.

Esto se hace atraves del `Jenkinsfile`, es parecido a los Dockerfile pero para Jenkins. Este archivo va en el repositorio de la aplicación que queramos configurar por Pipeline.

Se pueden configurar: tools, options, parámetros, y stages.

Las stages son muy importantes, es la forma en la que se le dice a Jenkis que ejecute los pasos del pipeline.

## Slaves

Los slaves permiten correr Jobs distribuidos. Sirve para cuando nuestro servidor queda sin recursos para ejecutar los Jobs en un solo nodo.

Un slave se conecta al Jenkins master, y el Jenkins master le delega trabajo al slave. Permite escalar horizontalmente.
