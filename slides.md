---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
background: https://images.unsplash.com/photo-1555109307-f7d9da25c244
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: true
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
---

# Docker and GitHub Actions

Camila Pozas - TechOps

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/camipozas" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>


---
layout: image-right
image: https://images.unsplash.com/photo-1541336032412-2048a678540d
---

# What is Docker?
It is a software platform that allows you to quickly build, test, and deploy applications.

- 📦 **Packages** Docker packages software into standardized units called containers that include everything needed for the software to run, including libraries, system tools, code, and runtime.
- 🐳 **Container** Really allows us to encapsulate, that is, pack software inside said container using the microservices architecture.

Read more about [Docker.](https://profile.es/blog/que_es_docker/)

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
}
</style>

---

# Process of creating a container in Docker

In addition, it is necessary to clarify that within the container a series of instructions **(dockerfile)** are defined that allow creating an image **(docker image)** with which to start said container **(docker container)**.[^1]

1. 🐳 **Dockerfile:** it is the text document on which we can group a series of commands so that they are all executed at the same time, thus avoiding having to execute them one by one manually so that the process of creating a Docker image is much easier. faster and more efficient.
2. 🖼️ **Docker image:** a Docker image, contains the libraries, along with the application code that contains everything necessary to run our application.
3. 📦 **Container:** It is a Docker image when it starts working, that is, when it comes to life.


<div id="centrado">
  <img src="https://profile.es/wp-content/media/image-1.png" align="right" width="600" height="600"/>
</div>

<style>
centrado {
  position: relative;
  margin: 0 auto;
  height: 100px;
  width: 100px;
}
</style>

[^1]: [Learn More](https://profile.es/blog/que_es_docker/)

---

# How to make a Dockerfile?
This file is made up of a series of commands that I will indicate below, and that are responsible for [building the image.](https://atareao.es/tutorial/docker/crear-tus-propias-imagenes-docker/)

### Docker Commands
|     |     |
| --- | --- |
<kbd>ADD</kbd> | copies a file from the host to the container.
<kbd>CMD</kbd> | the argument you pass by default.
<kbd>ENTRYPOINT</kbd> | the command that is executed by default when starting the container.
<kbd>ENV</kbd> | allows you to declare an environment variable in the container.
<kbd>EXPOSE</kbd> | open a container port.
<kbd>FROM</kbd> | indicates the base image that you will use to build your custom image. This option is required, and must also be the first instruction in the Dockerfile.

---

# Docker Commands
|     |     |
| --- | --- |
<kbd>MAINTAINER</kbd> | is an optional value that allows you to indicate who is in charge of maintaining the Dockerfile.
<kbd>ONBUILD</kbd> | allows you to indicate a command that is executed when your image is used to create another image.
<kbd>RUN</kbd> | run a command and save the result as a new layer.
<kbd>USER</kbd> | defines the default user of the container.
<kbd>VOLUME</kbd> | creates a volume that is shared by the different containers or with the host.
<kbd>WORKDIR</kbd> | defines the working directory for the container.

[Learn more](https://docs.docker.com/engine/reference/builder/)

---

# Basic Example

```docker {all|1-4|6-9|10-11|13|15-16|all}
FROM python:3.9

ENV APP_HOME /usr/src/app
WORKDIR /$APP_HOME

# Install python dependencies
COPY requirements.txt /tmp/
RUN pip install --requirement /tmp/requirements.txt
RUN pip freeze
# Copy env variables
ADD .env .env

COPY . $APP_HOME/

# Run
CMD python main.py
```
