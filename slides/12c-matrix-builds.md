# Matrix Builds

🔄 Run the **same job** across multiple configurations automatically.

```yaml
jobs:
  test:
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        node-version: [18, 20, 22]
        os: [ubuntu-latest, macos-latest]

    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node-version }}
      - run: npm ci
      - run: npm test
```

This generates **6 jobs** (3 versions × 2 OS).

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- The matrix automatically generates all possible combinations.
- Very useful for open source libraries that need to work across multiple versions.
- You can use `exclude` to skip specific combinations and `include` to add extra ones.
-->
