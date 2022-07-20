# Docker Commands
|     |     |     |
| --- | --- | --- |
**Command**[^1] | **Usage** | **Example**
list the most recently created images | <kbd>docker images</kbd>
docker tag | <kbd>docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG] </kbd> | <kbd>docker tag id_image camipozas/name_image:latest</kbd>
docker push | <kbd>docker push [OPTIONS] NAME[:TAG]</kbd> | <kbd>docker push camipozas/name_image </kbd>
docker pull | <kbd>docker pull [OPTIONS] NAME[:TAG]</kbd> | <kbd>docker pull camipozas/name_image </kbd>
docker exec | <kbd>docker exec [OPTIONS] CONTAINER COMMAND [ARG...]</kbd> | <kbd>docker exec -it container-name sh</kbd>

[^1]: [Docker Base Command](https://docs.docker.com/engine/reference/commandline/docker/) 

<link href="styles/style.css" rel="stylesheet" type="text/css" />