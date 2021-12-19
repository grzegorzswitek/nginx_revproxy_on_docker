FROM python:3.9-slim as my_django

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

ENV HOME=/usr/src/
WORKDIR $HOME

# install dependencies
RUN pip install --upgrade pip
COPY ./requirements.txt /usr/src/
RUN pip install -r /usr/src/requirements.txt
RUN django-admin startproject sample_project
WORKDIR /usr/src/sample_project/