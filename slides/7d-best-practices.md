# Docker Best Practices

### Do ✅

- Use **specific tags** (`node:22-alpine`, not `latest`)
- Use **multi-stage builds** to reduce image size
- Use **`COPY`** instead of `ADD`
- Combine `RUN` commands with `&&`
- Add **`HEALTHCHECK`** to your containers
- Run as **non-root user**

### Don't ❌

- Don't store **secrets** in the image
- Don't use `latest` tag in production
- Don't install **unnecessary packages**
- Don't run as **root**

```docker
# Run as non-root user
RUN addgroup --system app && adduser --system --ingroup app app
USER app
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- "latest" can change without warning and break your build.
- Multi-stage reduces size because you only copy the compiled output to the final stage.
- Running as root is a security risk — if someone exploits your container, they get root access.
- COPY is more predictable than ADD — ADD can extract archives and download URLs.
-->
