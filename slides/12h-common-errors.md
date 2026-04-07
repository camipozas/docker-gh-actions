# Common Errors & How to Fix Them

A quick reference for the most frequent problems you'll encounter.

### Docker

| Error | Why | Fix |
| --- | --- | --- |
| Port already in use | Another container is using that port | `docker ps` → stop it, or use a different port |
| Image not found | Wrong name or tag | Check the exact name on Docker Hub |
| Build fails | Wrong path or missing file | Make sure you run `docker build` from the right folder |

### GitHub Actions

| Error | Why | Fix |
| --- | --- | --- |
| Workflow doesn't run | Wrong branch or trigger | Check the `on:` section in your YAML |
| Secret not found | Typo or wrong scope | Go to Settings → Secrets and check the name |
| Permission denied | Missing permissions in workflow | Add `permissions: packages: write` |

### 💡 Tip

Always check the **Actions tab** in your repo to see the logs. The error message usually tells you exactly what went wrong.

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- This slide is a quick reference — come back to it when you run into problems.
- 90% of Docker errors are incorrect paths or ports already in use.
- 90% of GitHub Actions errors are misconfigured triggers or misspelled secrets.
- Always read the full logs — the answer is almost always there.
-->
