# Docker Hub

☁️ The world's largest container registry — **store, share, and distribute** Docker images.

```bash
# 1. Login to Docker Hub
docker login

# 2. Tag your image with your username
docker tag my-app:latest username/my-app:1.0.0

# 3. Push to Docker Hub
docker push username/my-app:1.0.0

# 4. Anyone can now pull your image
docker pull username/my-app:1.0.0
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Docker Hub is like "GitHub" but for Docker images.
- You need to create an account at hub.docker.com to push images.
- You can have public and private repositories.
-->
