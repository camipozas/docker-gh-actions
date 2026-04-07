# Docker Compose

🐙 Define and run **multi-container** applications with a single YAML file.

```yaml
services:
  app:
    build: .
    ports:
      - "3000:3000"
    depends_on:
      - db

  db:
    image: postgres:17-alpine
    volumes:
      - pgdata:/var/lib/postgresql/data

volumes:
  pgdata:
```

```bash
docker compose up -d      # Start in background
docker compose down        # Stop and remove
docker compose logs -f     # Follow logs
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- "docker compose" replaces "docker-compose" (with hyphen). The integrated version comes with Docker Desktop.
- depends_on defines the startup order, but it doesn't wait for the service to be "ready".
- Volumes persist data between container restarts.
- -d is detached mode (runs in background).
-->
