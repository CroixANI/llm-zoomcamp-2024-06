FROM mcr.microsoft.com/devcontainers/python:1-3.12-bullseye

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    ca-certificates \
    git \
    iputils-ping \
    && apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip install --upgrade pip
RUN pip install pipenv

ENV WORKDIR /app/

WORKDIR ${WORKDIR}

COPY .. $WORKDIR

RUN pipenv install --system --deploy --ignore-pipfile