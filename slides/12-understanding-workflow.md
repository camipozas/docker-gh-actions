# Understanding the [workflow](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions) file

```yaml{all|1|2-6|7-8|10-13|15-17|18-24|all}
name: Upload to S3
on:
  workflow_dispatch:
  push:
    branches:
      - main
  schedule:
    - cron: "0 4 * * *"

env:
  FRESH_TOKEN: ${{secrets.FRESH_TOKEN}}
  TESTRAIL_USER: ${{secrets.TESTRAIL_USER}}
  TESTRAIL_PASS: ${{secrets.TESTRAIL_PASS}}

jobs:
  upload:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Build docker images
        working-directory: ./testrail-freshdesk-api
        run: docker build -t local .
      - name: Run script and upload to S3
        run: docker run -e AWS_ACCESS_KEY_ID=${{ secrets.AWS_ACCESS_KEY_ID }} local
```
[Workflow Sintax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- workflow_dispatch: lets you manually trigger the workflow and optionally pass inputs.
- "upload" is just the name of the job.
- uses: actions/checkout@v4 — clones the code from the current branch.
- name: Build docker images — the label we give to the next action.
- working-directory: ./testrail-freshdesk-api — the folder where it runs.
- run: docker build -t local . — the command it will execute.
- -e passes an environment variable to the container, "local" is the image name.
-->