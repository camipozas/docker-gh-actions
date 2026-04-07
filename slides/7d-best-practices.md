---
layout: image-right
image: https://images.unsplash.com/photo-1504639725590-34d0984388bd
---

# Docker Best Practices

<div class="grid grid-cols-2 gap-4">
<div>

### Do ✅

- Use **specific tags** (`node:22-alpine`, not `node:latest`)
- Use **multi-stage builds** to reduce image size
- Use **`COPY`** instead of `ADD` (unless you need tar extraction)
- Combine `RUN` commands with `&&` to reduce layers
- Add **`HEALTHCHECK`** to your containers
- Run as **non-root user**

</div>
<div>

### Don't ❌

- Don't store **secrets** in the image
- Don't use `latest` tag in production
- Don't install **unnecessary packages**
- Don't run processes as **root**
- Don't ignore `.dockerignore`
- Don't use `ADD` when `COPY` is enough

</div>
</div>

```docker
# Example: non-root user
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
