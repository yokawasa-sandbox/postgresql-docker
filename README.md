# postgresql-docker
Docker Compose for PostgreSQL

## Quickstart

Spin up PostgreSQL on docker

```sh
docker compose up -d
```

List containers

```txt
docker-compose ps

NAME             IMAGE         COMMAND                   SERVICE   CREATED          STATUS          PORTS
local-postgres   postgres:15   "docker-entrypoint.s…"   db        20 minutes ago   Up 20 minutes   0.0.0.0:5432->5432/tcp, [::]:5432->5432/tcp
```

Test to connect postgreSQL instance (use 'postgres' for password)
```sh
psql -h localhost -U postgres -d sampledb
```


