---
layout: image-right
image: https://images.unsplash.com/photo-1589994965851-a8f479c573a9
---

# Debugging Containers

When something goes wrong, these three commands will help you find the problem.

```bash
# See what your app printed (logs, errors, etc)
docker logs my-app

# Open a terminal inside the container
docker exec -it my-app sh

# See all the container details (ports, env, network)
docker inspect my-app
```

### Common errors

| Error | What to do |
| --- | --- |
| Port already in use | Stop the other container or change the port |
| Image not found | Check the image name and tag |
| Permission denied | You might need to run as root or fix file permissions |

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- docker logs: this should always be the first thing you do. You'll see the errors there.
- docker exec -it: the -it flag is for interactive mode. "sh" opens a shell inside the container.
- docker inspect: shows EVERYTHING — ports, environment variables, network, volumes.
- If a port is in use, run "docker ps" to see which container is using it.
-->
