# Docker Hub

☁️ The world's largest container registry — **store, share, and distribute** Docker images.

```bash
docker login                                      # Login
docker tag my-app:latest username/my-app:1.0.0    # Tag
docker push username/my-app:1.0.0                 # Push
docker pull username/my-app:1.0.0                 # Pull
```

Other registries: **ghcr.io** (GitHub), **AWS ECR**, **Google Artifact Registry**

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Docker Hub is like "GitHub" but for Docker images.
- ghcr.io is very useful because it integrates directly with GitHub Actions.
- Companies usually use private registries (ECR, GCR) for security.
- You need to create an account at hub.docker.com to push images.
-->
