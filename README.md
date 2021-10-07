# RGBW to MQTT
Converts Home Assistant MQTT commands to RGBW channels

## Setup Steps
1. Create a [MQTT server](https://hub.docker.com/_/eclipse-mosquitto)
2. Setup config file `configuration.yml` in `/config` directory (example below)
3. Setup docker compose file (example below)
4. Run the app by running `docker-compose up --build`

## Example Docker Compose File
```
version: '3'
services:
  rgbw-mqtt:
    container_name: rgbw-mqtt
    image: matthewlarner/rgbw-mqtt:latest
    volumes:
      - ./config:/usr/src/app/config
    environment:
      - TZ=Australia/Sydney
    restart: always
```

## Example Config

Refer to https://github.com/matthew-larner/rgbw-mqtt/blob/main/configuration.yml.example

## How it works

This is a lightweight docker container which listens for MQTT commands from Home Assistant and converts them to RGBW channels.
