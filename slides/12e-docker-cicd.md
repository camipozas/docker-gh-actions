# Docker + GitHub Actions 🚀

A complete CI/CD workflow: **test → build → push** to GitHub Container Registry.

```yaml
name: CI/CD Pipeline
on:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 22
      - run: npm ci && npm test

  build-and-push:
    needs: test
    runs-on: ubuntu-latest
    permissions:
      packages: write
    steps:
      - uses: actions/checkout@v4
      - uses: docker/login-action@v3
        with:
          registry: ghcr.io
          username: ${{ github.actor }}
          password: ${{ secrets.GITHUB_TOKEN }}
      - uses: docker/build-push-action@v6
        with:
          push: true
          tags: ghcr.io/${{ github.repository }}:latest
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- needs: test makes build-and-push wait until the test job passes.
- GITHUB_TOKEN is an automatic secret — you don't need to create it.
- ghcr.io is GitHub's registry — the image gets linked to your repo.
-->
