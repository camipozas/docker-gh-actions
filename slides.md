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

<!--
# ¿Qué es Docker?
Es una plataforma de software que le permite crear, probar e implementar aplicaciones rápidamente.

- 📦 **Paquetes** Docker empaqueta el software en unidades estandarizadas llamadas contenedores que incluyen todo lo necesario para que se ejecute el software, incluidas bibliotecas, herramientas del sistema, código y tiempo de ejecución.
- 🐳 **Container** Realmente nos permite encapsular, es decir, empaquetar software dentro de dicho contenedor utilizando la arquitectura de microservicios.
-->
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

<!--
Además, es necesario aclarar que dentro del contenedor se definen una serie de instrucciones **(dockerfile)** que permiten crear una imagen **(docker image)** con la cual iniciar dicho contenedor **(docker container)**.

1. 🐳 **Dockerfile:** es el documento de texto sobre el que podemos agrupar una serie de comandos para que se ejecuten todos a la vez, evitando así tener que ejecutarlos uno a uno manualmente para que el proceso de creación una imagen de Docker es mucho más fácil. más rápido y más eficiente.
2. 🖼️ **Imagen de Docker:** una imagen de Docker, contiene las bibliotecas, junto con el código de la aplicación que contiene todo lo necesario para ejecutar nuestra aplicación.
3. 📦 **Contenedor:** Es una imagen de Docker cuando empieza a funcionar, es decir, cuando cobra vida.
-->

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

<!--
1. ADD | copia un archivo del host al contenedor.
2. CMD | el argumento que pasa por defecto.
3. ENTRYPOINT | el comando que se ejecuta por defecto al iniciar el contenedor.
4. ENV | le permite declarar una variable de entorno en el contenedor.
5. EXPOSE | abrir un puerto de contenedores.
6. FROM | indica la imagen base que utilizará para crear su imagen personalizada. Esta opción es obligatoria y también debe ser la primera instrucción en el Dockerfile.
-->
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

<!--
1. MAINTAINER | es un valor opcional que le permite indicar quién está a cargo del mantenimiento del Dockerfile.
2. ONBUILD | le permite indicar un comando que se ejecuta cuando su imagen se usa para crear otra imagen.
3. RUN | ejecute un comando y guarde el resultado como una nueva capa.
4. USER | define el usuario predeterminado del contenedor.
5. VOLUME | crea un volumen que es compartido por los diferentes contenedores o con el host.
6. WORKDIR | define el directorio de trabajo para el contenedor.
-->
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

<!--
- COPY . $APP_HOME/ lo que hace es:
- ENV APP_HOME /usr/src/app: crea esa carpeta en la imagen
- WORKDIR /$APP_HOME: crea esa carpeta en la imagen
-->
---

# Another Example

```docker {all|1-2|4-6|8-9|11-13|15-17|19-21|23-24|all}
FROM ubuntu:22.04 as base
FROM base as builder

#  Install Python
RUN apt update && apt install -y build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev
# Python install continues...

WORKDIR /opt/build
RUN apt update && apt-get install -y tesseract-ocr libtesseract-dev libleptonica-dev pkg-config poppler-utils

ADD requirements.txt requirements.txt
RUN pip install -r requirements.txt
ADD .env .env

# trained models
ADD tessdata/ tessdata/
ENV TESSDATA_PREFIX /opt/build/tessdata/

ADD app/ app/
RUN mkdir input
RUN mkdir output

ENTRYPOINT ["python"]
CMD ["app/main.py"]
```

<!--
En # Python install continues... le decimos que instale la versión, pip y todo lo necesario, esto se puede simplificar perfectamente si es que la imagen de docker ya existe.
- FROM base as builder: lo que hace es, parte de la imagen de arriba (en teoría se puede sacar, no hace nada)
- WORKDIR /opt/build: lo que hace es, crea esa carpeta y es donde trabajamos
- Por qué hay tmp en requirements y en el otro no? pq lo copié en tmp y en este no sino que donde estoy.
-->

---
layout: image-right
image: https://images.unsplash.com/photo-1600042863738-970c0d567f6b?
---

# GitHub Actions[^1]

GitHub Definition: _Automate, customize, and execute your software development workflows right in your repository with GitHub Actions. You can discover, create, and share actions to perform any job you'd like, including CI/CD, and combine actions in a completely customized workflow._[^2]

**But, what kind of things we can do?:** 
- Deploy docker images (or testing of multiple containers), CI/CD, automated PR workflows, connect to cloud services, it's **free**, etc.

**Why for us?**
- Because, we don't need to know too much about infrastructure.

[^1]:[Learn more](https://docs.github.com/en/actions)
[^2]: [Understanding GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions)

<!--
Definición de GitHub: _Automatice, personalice y ejecute sus flujos de trabajo de desarrollo de software directamente en su repositorio con GitHub Actions. Puede descubrir, crear y compartir acciones para realizar cualquier trabajo que desee, incluido CI/CD, y combinar acciones en un flujo de trabajo completamente personalizado._
-->

---

# How it works?

- **Workflows:** It's an automated procedure composed of one or more jobs that is added to a repository and can be activated by an event. They are defined by YAML files and with it you can build, test, package, relay or deploy a project.
- **Events:** Is a specific activity in a repository that triggers a workflow run. 
- **Jobs:** Is a set of steps in a workflow that execute on the same runner.
- **Actions:**  Is a custom application for the GitHub Actions platform that performs a complex but frequently repeated task.
- **Runners:** It is a machine with the GitHub Actions application already installed, whose function is to wait for the work to be available and then be able to execute the actions and report the progress and the results.

**Create an example workflow**
1. In your repository, create the <kbd>.github/workflows/</kbd> directory to store your workflow files.
2. In the <kbd>.github/workflows/</kbd> directory, create a new file called <kbd>learn-github-actions.yml</kbd> and add the following code.
  
<!--
- **Workflows:** es un proceso automatizado configurable que ejecutará uno o más jobs.
- **Events:** Un evento es una actividad específica en un repositorio, la cual activa una ejecución de flujo de trabajo.
- **Jobs:** es un conjunto de pasos en un flujo de trabajo, los cuales se ejecutan en el mismo ejecutor. Los pasos se ejecutarán en orden y serán dependientes uno del otro.
- **Actions:** es una aplicación personalizada para la plataforma de GitHub Actions que realiza una tarea compleja pero que se repite frecuentemente.
- **Runners:** es un servidor que ejecuta tus flujos de trabajo cuando se activan. Cada ejecutor puede ejecutar un job individual a la vez. GitHub proporciona ejecutores de Ubuntu Linux, Microsoft Windows y macOS para ejecutar tus flujos de trabajo; cada flujo de trabajo se ejecuta en una máquina virtual nueva y recién aprovisionada. Si necesitas un sistema operativo diferente o si requieres una configuración de hardware específica, puedes hospedar tus propios ejecutores. 
-->
---

# Understanding the workflow file[^1]

```yaml{all|1|2-6|7-8|10-13|15-17|18-24|all}
name: Upload to S3
on:
  workflow_dispatch:
  push:
    branches:
      - main
  schedule:
    - cron: "0 4 * * *"

env:
  FRESH_TOKEN: ${{secrets.FRESH_TOKEN}}
  TESTRAIL_USER: ${{secrets.TESTRAIL_USER}}
  TESTRAIL_PASS: ${{secrets.TESTRAIL_PASS}}

jobs:
  upload:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - name: Build docker images
        working-directory: ./testrail-freshdesk-api
        run: docker build -t local .
      - name: Run script and upload to S3
        run: docker run -e AWS_ACCESS_KEY_ID=${{ secrets.AWS_ACCESS_KEY_ID }} local
```

[^1]: [Workflow Sintax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)

<!--
- Al usar el evento <kbd>workflow_dispatch</kbd>, puede especificar opcionalmente las entradas que se pasan al flujo de trabajo.
- <kbd>upload</kbd> lo que hace, es el nombre del job
- <kbd>uses: actions/checkout@master</kbd>: lo que hace es, trae los códigos del branch donde estoy
- <kbd>- name: Build docker images</kbd>: el nombre que le damos a dicha acción a continuación.
- <kbd>working-directory: ./testrail-freshdesk-api</kbd>: donde lo está corriendo.
- <kbd>run: docker build -t local .</kbd>: lo que va a ejecutar
- <kbd>run: docker run -e AWS_ACCESS_KEY_ID=${{ secrets.AWS_ACCESS_KEY_ID }} local</kbd>: la <kbd>-e</kbd> es una variable de ambiente al contenedor y <kbd>local</kbd> es: el nombre de la imagen.
-->

---
layout: image-right
image: https://images.unsplash.com/photo-1541873676-a18131494184
---

# Why is it useful for us?

1. 💻 Sometimes our tools do not require a complex architecture, but they do need to be executed from time to time and injecting information elsewhere.
2. 📁 We only have to configure a <kbd>.yml</kbd> file and it's ready.
3. 🔐 We don't have a problem with environment variables because they are loaded into GitHub secrets ➡️ security.
4. 📚 There are many execution templates that help us make it even faster.
5. 🚀 We do not make the execution of the codes depend on us.

<!--
1. El panel de QA -> va a aws, si tuviera GPU podríamos correr los contratos quizás.
2. Puede ser una imagen o no dado que igual podemos correr un <kbd>main.py</kbd>
3. Estas sólo las carga el dueño del repo pero da lo mismo.
4. Está lleno en internet (de ahí me basé para el de Fresh).
5. Dejamos de lado que los códigos tengamos que correrlos en local.
-->