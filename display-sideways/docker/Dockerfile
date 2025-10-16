# Copyright 2025 Gregory Kiesel
# 
# support for Raspberry Pi 

FROM debian:bookworm

ARG DEBIAN_FRONTEND=noninteractive
ENV TZ="America/New_York"
RUN apt-get update 
RUN apt-get install -y tzdata
RUN apt-get install -y \ 
    python3 \
    python3-pip \
    python3-venv \
    git

    

# set up user
RUN useradd -r pi
WORKDIR /home/pi

# install pi-tft to image
RUN apt install -y
RUN python -m venv env --system-site-packages
RUN source env/bin/activate
RUN apt-get update
RUN pip3 install --upgrade adafruit-python-shell click Flask-SQLAlchemy
RUN git clone https://github.com/adafruit/Raspberry-Pi-Installer-Scripts.git

WORKDIR /home/pi/Raspberry-Pi-Installer-Scripts

RUN env PATH=$PATH python3 adafruit-pitft.py --display=28c --rotation=90 --install-type=mirror


WORKDIR /home/pi




