---
layout: image-right
image: https://images.unsplash.com/photo-1586528116311-ad8dd3c8310d
---

# Docker Hub

☁️ [Docker Hub](https://hub.docker.com/) is the world's largest container registry — a place to **store, share, and distribute** Docker images.

### Publishing an image

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

### Other registries

| Registry | Usage |
| --- | --- |
| **Docker Hub** | Public/private images, free tier available |
| **GitHub Container Registry (ghcr.io)** | Integrated with GitHub repos and Actions |
| **AWS ECR** | Private registry in AWS ecosystem |
| **Google Artifact Registry** | Private registry in GCP ecosystem |

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Docker Hub is like "GitHub" but for Docker images.
- ghcr.io is very useful because it integrates directly with GitHub Actions.
- Companies usually use private registries (ECR, GCR) for security.
- You need to create an account at hub.docker.com to push images.
-->
