# Common GitHub Actions Errors

- 🔴 **Workflow doesn't run**
  Check the `on:` section — wrong branch or trigger

- 🔴 **Secret not found**
  Check the name in Settings → Secrets (typos are common)

- 🔴 **Permission denied**
  Add `permissions: packages: write` to your job

- 🔴 **Action version not found**
  Use a valid version tag like `@v4`, not `@main`

💡 Always check the **Actions tab** in your repo for logs.

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- 90% of GitHub Actions errors are misconfigured triggers or misspelled secrets.
- Always read the full logs — the answer is almost always there.
- The Actions tab shows the full output of every step.
-->
