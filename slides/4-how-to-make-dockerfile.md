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
1. ADD | copia un archivo del host al contenedor.
2. CMD | el argumento que pasa por defecto.
3. ENTRYPOINT | el comando que se ejecuta por defecto al iniciar el contenedor.
4. ENV | le permite declarar una variable de entorno en el contenedor.
5. EXPOSE | abrir un puerto de contenedores.
6. FROM | indica la imagen base que utilizará para crear su imagen personalizada. Esta opción es obligatoria y también debe ser la primera instrucción en el Dockerfile.
-->