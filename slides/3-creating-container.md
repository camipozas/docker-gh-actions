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
- Inside the container, a series of instructions (Dockerfile) are defined to create an image (Docker image) to start the container (Docker container).
- Dockerfile: a text document where you group commands to be executed together, making image creation easier and faster.
- Docker image: contains libraries and application code — everything needed to run the app.
- Container: a Docker image when it starts running — when it comes to life.
-->