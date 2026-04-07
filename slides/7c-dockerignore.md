# .dockerignore

Just like `.gitignore`, this file tells Docker which files to **exclude** when building an image.

```text
node_modules
.git
.env
dist
coverage
Dockerfile
```

- 🚀 **Faster builds** — less files to send to Docker
- 🔒 **Security** — keeps secrets out of the image
- 📦 **Smaller images** — no unnecessary files

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- The build context is everything Docker sends to the daemon to build the image.
- Without .dockerignore, node_modules (which can be hundreds of MB) gets sent every time.
- Never include .env in the image — use environment variables at runtime instead.
-->
