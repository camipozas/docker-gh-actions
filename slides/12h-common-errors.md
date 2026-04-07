# Common Docker Errors

- 🔴 **Port already in use**
  `docker ps` → stop the other container or change port

- 🔴 **Image not found**
  Check the exact image name and tag on Docker Hub

- 🔴 **Build fails**
  Make sure you run `docker build` from the right folder

- 🔴 **Permission denied**
  You might need to run as root or fix file permissions

💡 Always run `docker logs <container>` first.

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- 90% of Docker errors are incorrect paths or ports already in use.
- docker logs is always the first thing you should check.
- If the port is in use, run "docker ps" to see which container is using it.
-->
