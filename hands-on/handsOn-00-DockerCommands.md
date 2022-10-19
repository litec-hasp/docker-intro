---
draft: true
---

# Quick Start

---

#### Docker - Get Started - Part 1

Details: <https://docs.docker.com/get-started/>

```bash
## List Docker CLI commands
docker
docker container --help
## Display Docker version and info
docker --version
docker version
docker info
## Execute Docker image
docker run hello-world
## List Docker images
docker image ls
## List Docker containers (running, all, all in quiet mode)
docker container ls
docker container ls --all
docker container ls -aq
```

---

#### Docker - Get Started - Part 2

Details: <https://docs.docker.com/get-started/part2>

Behandelt:

- Dockerfile
- Image / Container erzeugen

```bash
docker build -t friendlyhello .  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello  # Run "friendlyname" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyhello         # Same thing, but in detached mode
docker container ls                                # List all running containers
docker container ls -a             # List all containers, even those not running
docker container stop <hash>           # Gracefully stop the specified container
docker container kill <hash>         # Force shutdown of the specified container
docker container rm <hash>        # Remove specified container from this machine
docker container rm $(docker container ls -a -q)         # Remove all containers
docker image ls -a                             # List all images on this machine
docker image rm <image id>            # Remove specified image from this machine
docker image rm $(docker image ls -a -q)   # Remove all images from this machine
docker login             # Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag  # Tag <image> for upload to registry
docker push username/repository:tag            # Upload tagged image to registry
docker run username/repository:tag                   # Run image from a registry
```

---

#### Docker - Get Started - Part 3

Details: <https://docs.docker.com/get-started/part3>

Behandelt:

- docker compose
- swarm "Einstieg"

```bash
docker stack ls                                            # List stacks or apps
docker stack deploy -c <composefile> <appname>  # Run the specified Compose file
docker service ls                 # List running services associated with an app
docker service ps <service>                  # List tasks associated with an app
docker inspect <task or container>                   # Inspect task or container
docker container ls -q                                      # List container IDs
docker stack rm <appname>                             # Tear down an application
docker swarm leave --force      # Take down a single node swarm from the manager
```

---

#### TYOD - Try Your Own Docker

- **Get Started - Part 4, 5 und 6**
- **Container einrichten:**
  - ngnix Reverse Proxy
  - Traefik (Reverse Proxy)
  - MQTT Server
  - Nextcloud einrichten - mit **persistent data**!
  - Gitlab
  - CMS
  - LEMP bzw. LAMP aufgesplittet auf Container (zumindest DB extra)

- **Orchestration (Container Verwaltung):**

  - Kubernetes

