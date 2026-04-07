# How to make a Dockerfile?
This file is made up of a series of commands that I will indicate below, and that are responsible for [building the image.](https://atareao.es/tutorial/docker/crear-tus-propias-imagenes-docker/)

### Docker main commands
|     |     |
| --- | --- |
<kbd>ADD</kbd> | copies a file from the host to the container.
<kbd>CMD</kbd> | the argument you pass by default.
<kbd>ENTRYPOINT</kbd> | the command that is executed by default when starting the container.
<kbd>ENV</kbd> | allows you to declare an environment variable in the container.
<kbd>EXPOSE</kbd> | open a container port.
<kbd>FROM</kbd> | indicates the base image that you will use to build your custom image. This option is required, and must also be the first instruction in the Dockerfile.

<link href="styles/style.css" rel="stylesheet" type="text/css" />


<!--
1. ADD — copies a file from the host to the container.
2. CMD — the default argument passed to the container.
3. ENTRYPOINT — the command that runs by default when the container starts.
4. ENV — declares an environment variable inside the container.
5. EXPOSE — opens a container port.
6. FROM — sets the base image. This is required and must be the first instruction in the Dockerfile.
-->