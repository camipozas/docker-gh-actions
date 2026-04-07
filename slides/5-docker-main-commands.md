# Docker main commands
|     |     |
| --- | --- |
<kbd>LABEL</kbd> | adds metadata to the image (e.g. maintainer, version, description).
<kbd>HEALTHCHECK</kbd> | tells Docker how to check if the container is still working.
<kbd>ONBUILD</kbd> | allows you to indicate a command that is executed when your image is used to create another image.
<kbd>RUN</kbd> | run a command and save the result as a new layer.
<kbd>USER</kbd> | defines the default user of the container.
<kbd>VOLUME</kbd> | creates a volume that is shared by the different containers or with the host.
<kbd>WORKDIR</kbd> | defines the working directory for the container.

[Learn more](https://docs.docker.com/engine/reference/builder/)

<link href="styles/style.css" rel="stylesheet" type="text/css" />


<!--
1. LABEL — adds metadata to the image (e.g. maintainer, version, description). Replaces MAINTAINER (deprecated).
2. HEALTHCHECK — tells Docker how to check if the container is still working.
3. ONBUILD — runs a command when your image is used to create another image.
4. RUN — executes a command and saves the result as a new layer.
5. USER — sets the default user for the container.
6. VOLUME — creates a volume shared between containers or with the host.
7. WORKDIR — sets the working directory for the container.
-->