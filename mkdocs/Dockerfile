FROM python:3.6-alpine

LABEL name='MkDocs'
LABEL maintainer='Ryan Blunden <ryan.blunden@rabbitbird.com>'
LABEL version='latest'

RUN apk update && \
    apk upgrade && \
    apk add --no-cache python3 && \
    pip install --upgrade pip setuptools --trusted-host pypi.org --trusted-host files.pythonhosted.org && \
    rm -r /root/.cache

WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip install -r requirements.txt --trusted-host pypi.org --trusted-host files.pythonhosted.org && \
    rm -r /root/.cache

COPY . .

EXPOSE 8000

CMD ["mkdocs", "serve", "--dev-addr=0.0.0.0:8000"]
