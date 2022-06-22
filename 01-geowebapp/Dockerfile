# syntax=docker/dockerfile:1

FROM python:3.9-slim-buster

ENV PYTHONFAULTHANDLER 1

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y --no-install-recommends gcc

WORKDIR /src
COPY . .

RUN pip install pipenv
RUN pipenv lock -r > requirements.txt
RUN pip install -r requirements.txt

CMD ["greppo", "serve", "app.py", "--host=0.0.0.0"]
