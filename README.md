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

psql (17.2, server 15.14 (Debian 15.14-1.pgdg13+1))
Type "help" for help.

postgres=#
postgres=# \c
psql (17.2, server 15.14 (Debian 15.14-1.pgdg13+1))
You are now connected to database "postgres" as user "postgres".
postgres=# \l
```

> [!TIP]
> Setup `$HOME/.pgpass`
> 
> ```
> # hostname:port:database:username:password
> # Connnecting to sampledb with the same user and password
> # localhost:5432:sampledb:postgres:postgres
> # Connnecting to all databases with the same user and password
> localhost:5432:*:postgres:postgres
> ```
>
> Need to change the permission like this:
>
> ```sh
> chmod 600 ~/.pgpass
> ```
>
> Now you can login to "postgres" (default) database as user "postgres" w/o giving password input
>
> ```sh
> psql -U postgres -h localhost
> postgres=# \c
> psql (17.2, server 15.14 (Debian 15.14-1.pgdg13+1))
> You are now connected to database "postgres" as user "postgres".
> ```
