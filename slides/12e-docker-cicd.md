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
      - run: npm ci
      - run: npm test
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- This is the first job: it runs the tests.
- If tests fail, the build-and-push job won't run.
- actions/setup-node installs the specific Node.js version you need.
-->
