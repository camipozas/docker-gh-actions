---
layout: image-right
image: https://images.unsplash.com/photo-1555066931-4365d14bab8c
---

# Secrets & Variables

🔐 GitHub provides two ways to store configuration for your workflows.

<div class="grid grid-cols-2 gap-6">
<div>

### Secrets
- **Encrypted** values, never shown in logs
- For passwords, tokens, API keys
- Access: `${{ secrets.MY_SECRET }}`

**How to create:**
1. Go to repo → **Settings**
2. **Secrets and variables** → **Actions**
3. Click **New repository secret**

</div>
<div>

### Variables
- **Plain text**, visible in logs
- For non-sensitive config (URLs, flags)
- Access: `${{ vars.MY_VARIABLE }}`

**Scopes:**
- 🏢 **Organization** — shared across repos
- 📁 **Repository** — specific to one repo
- 🌍 **Environment** — per environment (prod, staging)

</div>
</div>

```yaml
steps:
  - name: Deploy
    env:
      API_KEY: ${{ secrets.API_KEY }}        # encrypted
      API_URL: ${{ vars.API_URL }}           # plain text
    run: ./deploy.sh
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Secrets are NEVER shown in logs — GitHub masks them automatically.
- Variables are newer (2023) — before, everything was done with secrets.
- Environment secrets are useful for having different values in prod vs staging.
- To create a secret: Settings → Secrets and variables → Actions → New repository secret.
-->
