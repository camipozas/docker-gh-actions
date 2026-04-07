# Docker Best Practices

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
- Running as root is a security risk — if someone exploits your container, they get root access.
- Always create a dedicated user for your application.
- Remove build dependencies after compilation to keep the image small.
-->
