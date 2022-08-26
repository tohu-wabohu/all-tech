FROM python:3.10.6-bullseye

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get upgrade -y && apt-get install -y \
  procps \
  iproute2 \
  dnsutils \
  iputils-ping \
  git \
  curl \
  wget \
  vim \
  # ---- other packages -----
  && rm -rf /var/lib/apt/lists/*

COPY _bashrc /root/.bashrc

COPY . /app
WORKDIR /app

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

CMD bash
