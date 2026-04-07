# Basic Example

```docker {all|1-4|6-9|10-11|13|15-16|all}
FROM python:3.13-slim

ENV APP_HOME /usr/src/app
WORKDIR $APP_HOME

# Install python dependencies
COPY requirements.txt /tmp/
RUN pip install --no-cache-dir --requirement /tmp/requirements.txt
RUN pip freeze
# Copy env variables
COPY .env .env

COPY . $APP_HOME/

# Run
CMD ["python", "main.py"]
```

<link href="styles/style.css" rel="stylesheet" type="text/css" />


<!--
- ENV APP_HOME /usr/src/app: sets an environment variable in the image (not included by default, for security).
- WORKDIR $APP_HOME: creates that folder in the image and sets it as the working directory.
- COPY . $APP_HOME/: copies all files from your machine into the image.
-->