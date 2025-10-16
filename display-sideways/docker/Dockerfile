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
    python3-pip
RUN pip3 install --upgrade adafruit-python-shell 

# set up user
RUN useradd -r pi
WORKDIR /home/pi

# install pi-tft to image
RUN pip3 install -y --upgrade adafruit-python-shell click Flask-SQLAlchemy
RUN git clone https://github.com/adafruit/Raspberry-Pi-Installer-Scripts.git
RUN python3 /home/pi/adafruit-pitft.py --display=28c --rotation=90 --install-type=mirror







