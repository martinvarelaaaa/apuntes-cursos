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
