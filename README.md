# docker-shadowsocks
Shadowsocks in Docker

Shadowsocks is a free and open-source encryption protocol project, widely used in mainland China to circumvent Internet censorship. It was created in 2012 by a Chinese programmer named “clowwindy”, and multiple implementations of the protocol have been made available since.

# Prerequisites
- Ubuntu 20.04+ (Recommended)

# Installation

First, update repository index and install docker.io and docker-compose

```
sudo apt update
sudo apt install docker.io docker-compose -y
sudo usermod -aG docker ubuntu
sudo su - $USER
```

# Install via Docker-Compose (Server)

```
sudo nano docker-compose.yml
```
```
version: "3.3"
services:
  shadowsocks:
    image: ghcr.io/antyung88/shadowsocks:main
    restart: always
    ports:
      - 8388:8388/tcp
      - 8388:8388/udp
    environment:
      - METHOD=aes-256-gcm
      - PASSWORD=password
```

Start service

```
docker-compose up -d
```

# Download Shadowsocks (Client)

https://shadowsocks.org/en/download/clients.html
