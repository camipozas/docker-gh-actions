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
      - uses: actions/checkout@master
      - name: Build docker images
        working-directory: ./testrail-freshdesk-api
        run: docker build -t local .
      - name: Run script and upload to S3
        run: docker run -e AWS_ACCESS_KEY_ID=${{ secrets.AWS_ACCESS_KEY_ID }} local
```
[Workflow Sintax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- Al usar el evento <kbd>workflow_dispatch</kbd>, puede especificar opcionalmente las entradas que se pasan al flujo de trabajo.
- <kbd>upload</kbd> lo que hace, es el nombre del job
- <kbd>uses: actions/checkout@master</kbd>: lo que hace es, trae los códigos del branch donde estoy
- <kbd>- name: Build docker images</kbd>: el nombre que le damos a dicha acción a continuación.
- <kbd>working-directory: ./testrail-freshdesk-api</kbd>: donde lo está corriendo.
- <kbd>run: docker build -t local .</kbd>: lo que va a ejecutar
- <kbd>run: docker run -e AWS_ACCESS_KEY_ID=${{ secrets.AWS_ACCESS_KEY_ID }} local</kbd>: la <kbd>-e</kbd> es una variable de ambiente al contenedor y <kbd>local</kbd> es: el nombre de la imagen.
-->