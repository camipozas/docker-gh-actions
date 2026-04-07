# Practical Exercise 🧪

### Challenge: Dockerize & Deploy

<div class="grid grid-cols-2 gap-6">
<div>

**Step 1 — Create a simple app**
- Create a Node.js/Python/TypeScript app
- Add a `GET /health` endpoint that returns `{ "status": "ok" }`

**Step 2 — Dockerize it**
- Write a `Dockerfile` (use multi-stage if applicable)
- Create a `.dockerignore` file
- Build and run locally:
```bash
docker build -t my-app .
docker run -p 3000:3000 my-app
```

</div>
<div>

**Step 3 — Automate with GitHub Actions**
- Push your code to GitHub
- Create `.github/workflows/ci.yml`
- The workflow should:
  - ✅ Run tests on every PR
  - 🐳 Build the Docker image
  - 📦 Push to `ghcr.io` on merge to `main`

**Bonus**
- Add a `docker-compose.yml` with a database
- Add a matrix build for multiple Node versions
- Add a `HEALTHCHECK` to your Dockerfile

</div>
</div>

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- This exercise covers everything we saw in the presentation.
- You can work in groups or individually.
- The bonus is for those who finish early.
-->
