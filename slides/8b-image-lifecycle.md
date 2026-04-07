---
layout: image-right
image: https://images.unsplash.com/photo-1527515637462-cee1aa7740b1
---

# Cleaning Up

Docker images take up space on your computer. Here's how to clean up.

```bash
# See all your images and their sizes
docker images

# Delete everything unused (containers, images, networks)
docker system prune

# Delete only unused images
docker image prune

# See how much space Docker is using
docker system df
```

### 💡 Tip

Run `docker system prune` once a week to keep your disk clean.

Add `-a` to also remove images that aren't being used by any container:

```bash
docker system prune -a
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Images accumulate quickly, especially if you do many builds.
- docker system prune only deletes what's not being used — it's safe.
- With -a it deletes EVERYTHING without an active container. Be careful if you have images you want to keep.
- docker system df is like "du" but for Docker — shows how much space each thing uses.
-->
