---
layout: image-right
image: https://images.unsplash.com/photo-1586197403936-bef0b84d9739
---

# Key Terms Related To Docker Commands

1. ☁️ **Docker Hub:** A public registry for developers to distribute their code.
2. <kbd>[OPTIONS]</kbd>: you can add options to your commands to get different results. Each command has lots of options associated with it. Refer to the documentation for all the details.
3. <kbd>[COMMAND]</kbd>: you put the parameters for your command. Depending on the command, it might be a file name or a container ID.
4. <kbd>[ARG…]</kbd>: you can write additional arguments for a command.

<link href="styles/style.css" rel="stylesheet" type="text/css" />
---

# Docker Commands
|     |     |     |
| --- | --- | --- |
**Command**[^1] | **Usage** | **Example**
docker build[^2] | <kbd>docker build [OPTIONS] [directory/path/URL]</kbd> | <kbd>docker build -t name_image .</kbd>
docker run | <kbd>docker run [OPTIONS] IMAGE [COMMAND] [ARG...]</kbd> | <kbd>docker run name_image</kbd>
docker stop | <kbd>docker stop [OPTIONS] CONTAINER [...]</kbd> | <kbd>docker stop my_container</kbd>
list the docker containers available. | <kbd>docker ps [OPTIONS] </kbd>
removes a container | <kbd>docker rm [OPTIONS] CONTAINER [CONTAINER...]</kbd> | <kbd>docker rm my_container</kbd>

[^1]: [Docker Base Command](https://docs.docker.com/engine/reference/commandline/docker/) 
[^2]: [Docker build](https://docs.docker.com/engine/reference/commandline/build/)

<link href="styles/style.css" rel="stylesheet" type="text/css" />
