# Process of creating a container in Docker

In addition, it is necessary to clarify that within the container a series of instructions **(dockerfile)** are defined that allow creating an image **(docker image)** with which to start said container **(docker container)**.[^1]

1. 🐳 **Dockerfile:** it is the text document on which we can group a series of commands so that they are all executed at the same time, thus avoiding having to execute them one by one manually so that the process of creating a Docker image is much easier. faster and more efficient.
2. 🖼️ **Docker image:** a Docker image, contains the libraries, along with the application code that contains everything necessary to run our application.
3. 📦 **Container:** It is a Docker image when it starts working, that is, when it comes to life.


<div id="centrado">
  <img src="/images/docker-flow.png" align="right" width="600" height="600"/>
</div>

<style>
centrado {
  position: relative;
  margin: 0 auto;
  height: 100px;
  width: 100px;
}
</style>

<link href="styles/style.css" rel="stylesheet" type="text/css" />

[^1]: [Learn More](https://profile.es/blog/que_es_docker/)

<!--
Además, es necesario aclarar que dentro del contenedor se definen una serie de instrucciones **(dockerfile)** que permiten crear una imagen **(docker image)** con la cual iniciar dicho contenedor **(docker container)**.

1. 🐳 **Dockerfile:** es el documento de texto sobre el que podemos agrupar una serie de comandos para que se ejecuten todos a la vez, evitando así tener que ejecutarlos uno a uno manualmente para que el proceso de creación una imagen de Docker es mucho más fácil. más rápido y más eficiente.
2. 🖼️ **Imagen de Docker:** una imagen de Docker, contiene las bibliotecas, junto con el código de la aplicación que contiene todo lo necesario para ejecutar nuestra aplicación.
3. 📦 **Contenedor:** Es una imagen de Docker cuando empieza a funcionar, es decir, cuando cobra vida.
-->