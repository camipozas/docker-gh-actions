# Docker + GitHub Actions 🚀

The **build-and-push** job — only runs after tests pass.

```yaml
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
- needs: test makes this job wait until the test job passes.
- GITHUB_TOKEN is an automatic secret — you don't need to create it.
- ghcr.io is GitHub's registry — the image gets linked to your repo.
-->
