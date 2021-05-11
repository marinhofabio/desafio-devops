FROM python:3.7.4-alpine3.10

MAINTAINER Fabio Marinho <marinho.fabio@gmail.com>

COPY requirements.txt /usr/src/app/requirements.txt

RUN pip install --upgrade pip && pip install --no-cache-dir -r /usr/src/app/requirements.txt

COPY api.py /usr/src/app

WORKDIR /usr/src/app

CMD ["gunicorn", "--log-level", "debug", "--bind", ":8000", "--workers", "1", "api:app"]

EXPOSE 8000/tcp
