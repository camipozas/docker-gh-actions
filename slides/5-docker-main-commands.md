# Docker main commands
|     |     |
| --- | --- |
<kbd>MAINTAINER</kbd> | is an optional value that allows you to indicate who is in charge of maintaining the Dockerfile.
<kbd>ONBUILD</kbd> | allows you to indicate a command that is executed when your image is used to create another image.
<kbd>RUN</kbd> | run a command and save the result as a new layer.
<kbd>USER</kbd> | defines the default user of the container.
<kbd>VOLUME</kbd> | creates a volume that is shared by the different containers or with the host.
<kbd>WORKDIR</kbd> | defines the working directory for the container.

[Learn more](https://docs.docker.com/engine/reference/builder/)

<link href="styles/style.css" rel="stylesheet" type="text/css" />


<!--
1. MAINTAINER | es un valor opcional que le permite indicar quién está a cargo del mantenimiento del Dockerfile.
2. ONBUILD | le permite indicar un comando que se ejecuta cuando su imagen se usa para crear otra imagen.
3. RUN | ejecute un comando y guarde el resultado como una nueva capa.
4. USER | define el usuario predeterminado del contenedor.
5. VOLUME | crea un volumen que es compartido por los diferentes contenedores o con el host.
6. WORKDIR | define el directorio de trabajo para el contenedor.
-->