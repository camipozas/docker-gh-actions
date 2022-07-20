# Basic Example

```docker {all|1-4|6-9|10-11|13|15-16|all}
FROM python:3.9

ENV APP_HOME /usr/src/app
WORKDIR /$APP_HOME

# Install python dependencies
COPY requirements.txt /tmp/
RUN pip install --requirement /tmp/requirements.txt
RUN pip freeze
# Copy env variables
ADD .env .env

COPY . $APP_HOME/

# Run
CMD python main.py
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />


<!--
- ENV APP_HOME /usr/src/app: dice que la imagen va a tener una variable de ambiente (no lo trae por defecto, seguridad).
- WORKDIR /$APP_HOME: crea esa carpeta en la imagen
- COPY . $APP_HOME/ lo que hace es: copia todos los archivos pero allá (en la imagen).
-->