# Another Example

```docker {all|1-2|4-6|8-9|11-13|15-17|19-21|23-24|all}
FROM ubuntu:24.04 AS base
FROM base AS builder

#  Install Python
RUN apt-get update && apt-get install -y --no-install-recommends build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev && rm -rf /var/lib/apt/lists/*
# Python install continues...

WORKDIR /opt/build
RUN apt-get update && apt-get install -y --no-install-recommends tesseract-ocr libtesseract-dev libleptonica-dev pkg-config poppler-utils && rm -rf /var/lib/apt/lists/*

COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt
COPY .env .env

# trained models
COPY tessdata/ tessdata/
ENV TESSDATA_PREFIX=/opt/build/tessdata/

COPY app/ app/
RUN mkdir input && mkdir output

ENTRYPOINT ["python"]
CMD ["app/main.py"]
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />

<!--
- "Python install continues..." means we install Python, pip, and everything needed. This can be simplified if a Python Docker image already exists.
- FROM base AS builder: starts from the base image above (in theory it can be removed, it doesn't add anything).
- WORKDIR /opt/build: creates that folder and sets it as the working directory.
- Why is there /tmp in one requirements copy but not the other? Because one copies to /tmp, the other copies to the current directory.
-->