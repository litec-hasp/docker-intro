# Docker Compose

A short overview

---

## What is Docker Compose?

- **Utility to run *multiple containers* as a system of containers.**
- Run
  - your application in one container,
  - your database in another,
  - and your analytics application in a third container.
- Takes care of:
  - proper connection and awareness between containers
  - network settings,
  - volume settings.

---

## Docker Compose File Structure

- Structure: [YAML](https://yaml.org/) (.yml) file
- Name: `compose.yml` or `docker-compose.yml`
- **Beware! Indentation is important!**

### Example

```yaml
version: 'X'

services:
  web:
    build: .
    ports:
     - "5000:5000"
    volumes:
     - .:/code
  database:
    image: redis

networks:
  default:
    name: my-pre-existing-network
    external: true
```

Note:

@todo add explanations!

---

## Exercises and Further Reading

### Exercises

- [Get started with Docker Compose](https://docs.docker.com/compose/gettingstarted/)
  - official docker intro with flask (python) and redis
- **A MUST TRYOUT**: [Github - awesome-compose](https://github.com/docker/awesome-compose)
  - a lot of templates to look at...
- A BIG one - has it all: [Tutorial: Full Stack Web App](https://milanwittpohl.com/projects/tutorials/full-stack-web-app/)
  - java spring backend / nuxtjs frontend / ...

### Further Reading

- [Educative - Docker Compose Tutorial](https://www.educative.io/blog/docker-compose-tutorial)
