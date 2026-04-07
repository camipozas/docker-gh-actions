# Matrix Builds

🔄 Run the **same job** across multiple configurations automatically.

```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [18, 20, 22]

    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node-version }}
      - run: npm ci
      - run: npm test
```

This generates **3 jobs** automatically, one per version.

### When to use it?

- 📦 Test across **multiple versions**
- 💻 Build for **multiple OS**
- 🧪 Test with **different databases**

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- The matrix automatically generates all possible combinations.
- Very useful for open source libraries that need to work across multiple versions.
- You can use `exclude` to skip specific combinations and `include` to add extra ones.
-->
