# syntax=docker/dockerfile:1
FROM python:3.7-alpine
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
WORKDIR /code
COPY requirements.txt /code/
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories
RUN apk update && apk add --no-cache postgresql-dev gcc python3-dev musl-dev
RUN pip install --upgrade pip -i https://mirrors.aliyun.com/pypi/simple
RUN pip install -r requirements.txt -i https://mirrors.aliyun.com/pypi/simple
COPY . /code/