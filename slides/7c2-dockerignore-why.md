# Why .dockerignore?

- 🚀 **Faster builds** — less files to send to Docker
- 🔒 **Security** — keeps secrets (`.env`) out of the image
- 📦 **Smaller images** — no unnecessary files

Without `.dockerignore`, Docker sends **everything** in your folder to build the image — including `node_modules` (hundreds of MB).

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- The build context is sent to the Docker daemon every time you run docker build.
- A large context makes builds slow, especially on CI/CD where there's no local cache.
- Always exclude test files, docs, and dev dependencies from production images.
-->
