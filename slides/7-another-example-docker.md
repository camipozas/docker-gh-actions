# Another Example

```docker {all|1-2|4-6|8-9|11-13|15-17|19-21|23-24|all}
FROM ubuntu:22.04 as base
FROM base as builder

#  Install Python
RUN apt update && apt install -y build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev
# Python install continues...

WORKDIR /opt/build
RUN apt update && apt-get install -y tesseract-ocr libtesseract-dev libleptonica-dev pkg-config poppler-utils

ADD requirements.txt requirements.txt
RUN pip install -r requirements.txt
ADD .env .env

# trained models
ADD tessdata/ tessdata/
ENV TESSDATA_PREFIX /opt/build/tessdata/

ADD app/ app/
RUN mkdir input
RUN mkdir output

ENTRYPOINT ["python"]
CMD ["app/main.py"]
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
En # Python install continues... le decimos que instale la versión, pip y todo lo necesario, esto se puede simplificar perfectamente si es que la imagen de docker ya existe.
- FROM base as builder: lo que hace es, parte de la imagen de arriba (en teoría se puede sacar, no hace nada)
- WORKDIR /opt/build: lo que hace es, crea esa carpeta y es donde trabajamos
- Por qué hay tmp en requirements y en el otro no? pq lo copié en tmp y en este no sino que donde estoy.
-->