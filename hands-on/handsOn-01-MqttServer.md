---
draft: true - atm not tested
---

# Setup A Mqtt Server

with docker-compose (*work in progress*)

---

### Step 1- Install Compose / Setup MQTT CLient

Follow: <https://docs.docker.com/compose/install/>
and <https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-the-mosquitto-mqtt-messaging-broker-on-debian-9>

Note: TBD improve slide

---

### A docker-compose.yml file example

```dockerfile
version: '3'

services:
  mosquitto:
    image: eclipse-mosquitto:latest    
    container_name: mosquitto
    restart: unless-stopped
    security_opt:
      - no-new-privileges:true
    networks:
      - mqtt
    ports:
      - 1883:1883
      - 9001:9001
    volumes:
      - /etc/localtime:/etc/localtime:ro
      - ${USER_DIR}/data/mosquitto/config/mosquitto.conf:/mosquitto/config/mosquitto.conf:ro
      - ${USER_DIR}/data/mosquitto/log:/mosquitto/log
      - mqtt_data:/mosquitto/data
          

networks:
  mqtt:
    external: true

volumes:
  mqtt_data:
```

---

### Setup Environment Variables on Linux

1. ssh to your docker-toolbox (IP is most of the time something like 192.168.99.100)
2. edit/create `/etc/environment`:

    ```bash
    sudo vi /etc/environment
    ```

3. and add the following line:

    ```bash
    USERDIR="/home/docker"
    ```

---

### Setup Network Bridge for Mqtt (VS Code)

1. switch to Docker sideboard
2. click `+` (create) on Network "Box"
3. choose Bridge and name it `mqtt`
