# Common Errors

### Docker

| Error | Fix |
| --- | --- |
| Port already in use | `docker ps` → stop it or change port |
| Image not found | Check the name on Docker Hub |
| Build fails | Run `docker build` from the right folder |

### GitHub Actions

| Error | Fix |
| --- | --- |
| Workflow doesn't run | Check the `on:` section |
| Secret not found | Check name in Settings → Secrets |
| Permission denied | Add `permissions: packages: write` |

💡 Always check the **Actions tab** for logs.

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- This slide is a quick reference — come back to it when you run into problems.
- 90% of Docker errors are incorrect paths or ports already in use.
- 90% of GitHub Actions errors are misconfigured triggers or misspelled secrets.
- Always read the full logs — the answer is almost always there.
-->
