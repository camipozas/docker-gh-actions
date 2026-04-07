---
layout: image-right
image: https://images.unsplash.com/photo-1461685265823-f8d5d0b08b9b
---

# Faster Workflows

Installing dependencies every time is slow. **Cache** saves them so the next run is faster.

```yaml
- uses: actions/cache@v4
  with:
    path: node_modules
    key: deps-${{ hashFiles('pnpm-lock.yaml') }}

- run: pnpm install
```

⚡ Without cache: **3 min** → With cache: **30 sec**

### Artifacts

Pass files between jobs or download them after the workflow finishes.

```yaml
- uses: actions/upload-artifact@v4
  with:
    name: build-output
    path: dist/
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Cache stores node_modules and reuses it if the lockfile hasn't changed.
- hashFiles generates a hash of the lockfile — if it changes, dependencies are reinstalled.
- Artifacts are files you can download after the workflow finishes (builds, reports, logs).
- upload-artifact uploads files, download-artifact downloads them in another job.
-->
