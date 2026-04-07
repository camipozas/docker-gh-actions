---
layout: image-right
image: https://images.unsplash.com/photo-1453928582365-b6ad33cbcf64
---

# .dockerignore

Just like `.gitignore`, the `.dockerignore` file tells Docker which files to **exclude** when building an image.

```text
node_modules
npm-debug.log
.git
.gitignore
.env
.env.*
dist
coverage
*.md
Dockerfile
docker-compose.yml
.dockerignore
```

### Why is it important?

- 🚀 **Faster builds** — reduces the build context size sent to the Docker daemon
- 🔒 **Security** — prevents secrets (`.env`, credentials) from being copied into the image
- 📦 **Smaller images** — avoids unnecessary files in the final image

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- The build context is everything Docker sends to the daemon to build the image.
- Without .dockerignore, node_modules (which can be hundreds of MB) gets sent every time.
- Never include .env in the image — use environment variables at runtime instead.
-->
