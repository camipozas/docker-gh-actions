# .dockerignore

Just like `.gitignore`, this file tells Docker which files to **exclude** when building an image.

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

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- The build context is everything Docker sends to the daemon to build the image.
- Without .dockerignore, node_modules (which can be hundreds of MB) gets sent every time.
- Never include .env in the image — use environment variables at runtime instead.
-->
