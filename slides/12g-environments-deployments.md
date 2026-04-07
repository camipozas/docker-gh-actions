# Deploying Safely

**Environments** let you have different settings for staging and production.

```yaml
jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: production
    steps:
      - uses: actions/checkout@v4
      - run: ./deploy.sh
```

### Protection rules

You can require **approval** before deploying to production:

1. Go to **Settings** → **Environments**
2. Create `production` environment
3. Add **Required reviewers** ✅

Each environment can have its own **secrets** and **variables**.

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Staging is for testing before sending to production.
- With required reviewers, someone on the team must approve the deploy manually.
- Each environment can have its own secrets — for example, a different API key for staging and prod.
- This prevents accidentally deploying broken code to production.
-->
