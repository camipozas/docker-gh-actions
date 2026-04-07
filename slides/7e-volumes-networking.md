---
layout: image-right
image: https://images.unsplash.com/photo-1494412574643-ff11b0a5eb19
---

# Volumes & Networking

### Volumes

Containers lose their data when they stop. **Volumes** save your data outside the container.

```bash
# Named volume — Docker manages it for you
docker run -v mydata:/app/data my-app

# Bind mount — links a folder from your computer
docker run -v ./local-folder:/app/data my-app
```

### Networking

Containers in the same Compose file can talk to each other **by name**.

```yaml
# app connects to the database using "db" as hostname
environment:
  - DATABASE_URL=postgres://user:pass@db:5432/mydb
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Without a volume, every time you stop a container all data is lost (databases, uploaded files, etc).
- Named volume: Docker stores it internally. Bind mount: you choose the folder on your machine.
- In Compose, "db" is the service name and Docker resolves it like a hostname.
- You don't need to know the container's IP — just use the service name.
-->
