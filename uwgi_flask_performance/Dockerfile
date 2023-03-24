FROM python:3.11-slim

ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1

RUN mkdir /app
WORKDIR /app
ADD ./requirements.txt ./

RUN apt update && apt install -y python3-pip    \
    && pip3 install -r ./requirements.txt \
    && pip3 install uwsgi \
    && rm -rf /var/lib/apt/lists/*

EXPOSE 8000

CMD ["uwsgi", "--show-config", "--ini", "/app/uwsgi.ini"]