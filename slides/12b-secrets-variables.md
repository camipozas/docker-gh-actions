# Secrets & Variables

🔐 Two ways to store configuration for your workflows.

### Secrets (encrypted, hidden in logs)
- For passwords, tokens, API keys
- Access: `${{ secrets.MY_SECRET }}`

### Variables (plain text, visible in logs)
- For non-sensitive config (URLs, flags)
- Access: `${{ vars.MY_VARIABLE }}`

```yaml
steps:
  - name: Deploy
    env:
      API_KEY: ${{ secrets.API_KEY }}
      API_URL: ${{ vars.API_URL }}
    run: ./deploy.sh
```

Create them in: **Settings** → **Secrets and variables** → **Actions**

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Secrets are NEVER shown in logs — GitHub masks them automatically.
- Variables are newer (2023) — before, everything was done with secrets.
- Environment secrets are useful for having different values in prod vs staging.
- To create a secret: Settings → Secrets and variables → Actions → New repository secret.
-->
