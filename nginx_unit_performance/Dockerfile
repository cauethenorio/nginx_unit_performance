FROM nginx/unit:1.29.1-python3.11

ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1

RUN mkdir /app
WORKDIR /app
ADD ./requirements.txt ./

RUN apt update && apt install -y python3-pip    \
    && pip3 install -r ./requirements.txt \
    && rm -rf /var/lib/apt/lists/*


ADD config.json /docker-entrypoint.d/config.json


