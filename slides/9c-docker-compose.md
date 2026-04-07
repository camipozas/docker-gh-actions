# Docker Compose

🐙 Define and run **multi-container** applications with a single YAML file.

```yaml
services:
  app:
    build: .
    ports:
      - "3000:3000"
    environment:
      - DATABASE_URL=postgres://user:pass@db:5432/mydb
    depends_on:
      - db
      - redis

  db:
    image: postgres:17-alpine
    volumes:
      - pgdata:/var/lib/postgresql/data
    environment:
      - POSTGRES_PASSWORD=pass

  redis:
    image: redis:7-alpine

volumes:
  pgdata:
```

```bash
docker compose up -d      # Start all services in background
docker compose down        # Stop and remove containers
docker compose logs -f     # Follow logs from all services
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- "docker compose" replaces "docker-compose" (with hyphen). The integrated version comes with Docker Desktop.
- depends_on defines the startup order, but it doesn't wait for the service to be "ready".
- Volumes persist data between container restarts.
- -d is detached mode (runs in background).
-->
