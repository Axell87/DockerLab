# Create image from Base python 3.8 version
FROM python:3.8-slim as base
FROM base as builder
# Create Dir
RUN mkdir /install
# Setup workdir in container
WORKDIR /install

#Copy requirements to dir and install packages from req
COPY requirements.txt .
RUN pip install --upgrade pip
RUN pip install --prefix=/install -r requirements.txt
#Copy dir to folder
FROM base
COPY --from=builder /install /usr/local
#Add ENV
ENV PYTHONBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1
#Copy app
WORKDIR /app
COPY . .
#Run CMD in container on 8000 port
CMD python manage.py runserver 0.0.0.0:8000