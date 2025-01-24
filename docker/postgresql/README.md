# Postgresql

This deployment sets up a PostgreSQL cluster consisting of a primary node and a replica node, relying on an overlay network and managed via Docker Swarm and Docker Compose.


> Prerequisite : change docker compose variables

&nbsp;


## Deploy PostgreSQL service with docker swarm
```bash
docker stack deploy -c /docker/postgresql/docker-compose.yml postgres
```


```markdown
# PostgreSQL Cluster with Replication

Deploy a PostgreSQL cluster with replication using Docker Swarm and the Bitnami PostgreSQL Repmgr image.

## Prerequisites

- **Docker Swarm**: Ensure Docker Swarm is initialized.
- **Overlay Network**: Create a network for the cluster:
  ```bash
  docker network create --driver overlay postgres_net
  ```
- **Environment Variables**: Define these variables:
  - `POSTGRESQL_POSTGRES_PASSWORD`
  - `POSTGRESQL_USERNAME`
  - `POSTGRESQL_PASSWORD`
  - `POSTGRESQL_DATABASE`
  - `REPMGR_PASSWORD`

## Deployment Steps

1. Save the `docker-compose.yml` file.
2. Deploy the stack with:
   ```bash
   docker stack deploy -c docker-compose.yml postgres-cluster
   ```
3. Verify the cluster status:
   ```bash
   docker exec -it <container-name> repmgr cluster show
   ```

## Services

- **Primary Node**: `postgresql-primary`
  - Handles database writes and replication.
  - Exposes port `5432`.
- **Replica Node**: `postgresql-replica`
  - Replicates data from the primary.

## Storage

- **Persistent Volumes**:
  - `postgres_primary_data`: For the primary node.
  - `postgres_replica_data`: For the replica node.

```
