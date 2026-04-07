# Docker Compose Commands

```bash
# Start all services in background
docker compose up -d

# Stop and remove containers
docker compose down

# Follow logs from all services
docker compose logs -f

# Rebuild images and restart
docker compose up -d --build
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- -d is detached mode (runs in background).
- "docker compose down" stops and removes containers, networks, but keeps volumes.
- Add --build when you change the Dockerfile and want to rebuild.
- "docker compose logs -f" is like "tail -f" for all your services at once.
-->
