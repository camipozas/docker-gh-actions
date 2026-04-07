# Docker Hub

☁️ The world's largest container registry — **store, share, and distribute** Docker images.

```bash
# 1. Login
docker login

# 2. Tag your image
docker tag my-app:latest username/my-app:1.0.0

# 3. Push to Docker Hub
docker push username/my-app:1.0.0

# 4. Anyone can pull it
docker pull username/my-app:1.0.0
```

### Other registries

| Registry | When to use |
| --- | --- |
| **Docker Hub** | Public images, open source |
| **ghcr.io** | Integrated with GitHub |
| **AWS ECR** | Private, AWS projects |

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Docker Hub is like "GitHub" but for Docker images.
- ghcr.io is very useful because it integrates directly with GitHub Actions.
- Companies usually use private registries (ECR, GCR) for security.
- You need to create an account at hub.docker.com to push images.
-->
