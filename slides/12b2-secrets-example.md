# Using Secrets & Variables

```yaml
steps:
  - name: Deploy
    env:
      API_KEY: ${{ secrets.API_KEY }}
      API_URL: ${{ vars.API_URL }}
    run: ./deploy.sh
```

### Scopes

- 🏢 **Organization** — shared across repos
- 📁 **Repository** — specific to one repo
- 🌍 **Environment** — per environment (prod, staging)

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Environment secrets are useful for having different values in prod vs staging.
- Organization secrets are shared across all repos in the org.
- Repository secrets override organization secrets with the same name.
-->
