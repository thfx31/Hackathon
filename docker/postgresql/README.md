# Postgresql

This deployment sets up a PostgreSQL cluster consisting of a primary node and a replica node, relying on an overlay network and managed via Docker Swarm and Docker Compose.


> Prerequisite : change docker compose variables

&nbsp;


## Deploy PostgreSQL service with docker swarm
```bash
docker stack deploy -c /docker/postgresql/docker-compose.yml postgres
```