---
layout: image-right
image: https://images.unsplash.com/photo-1558494949-ef010cbdcc31
---

# Matrix Builds

🔄 Run the **same job** across multiple configurations automatically.

```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [18, 20, 22]
        os: [ubuntu-latest, macos-latest]

    steps:
      - uses: actions/checkout@v4
      - name: Setup Node.js ${{ matrix.node-version }}
        uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node-version }}
      - run: npm ci
      - run: npm test
```

This generates **6 jobs** automatically (3 versions × 2 OS).

### When to use it?

- 📦 Test your library across **multiple Node/Python versions**
- 💻 Build for **multiple operating systems**
- 🧪 Run tests with **different databases** (PostgreSQL, MySQL)

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- The matrix automatically generates all possible combinations.
- Very useful for open source libraries that need to work across multiple versions.
- You can use `exclude` to skip specific combinations and `include` to add extra ones.
-->
