# Metabase Compose

## About

This document does not explain how to use Metabase, please refer to the official documentation for usage instructions.

The Compose uses the following images:

+ [Metabase](https://hub.docker.com/r/metabase/metabase)
+ [Postgres](https://hub.docker.com/_/postgres)
+ [MySQL](https://hub.docker.com/_/mysql)
+ [Adminer](https://hub.docker.com/_/adminer)

> The database images (`mysql`, `postgres`) are created via dockerfiles that a wrap the official images.

### Configuration

Container configurations depend on environment variables defined in an `.env` file.

+ Copy the `.env.example` file and rename it to `.env`
+ Replace the environment values to your desire. See environment explanatory chart below

### Environment variables

Database environment:

+ `DB_TYPE:` can be either `postgres` or `mysql`
+ `DB_NAME:` the name of the database
+ `DB_USER:` a database user different than root
+ `DB_PASSWORD:` a password for `DB_USER`
+ `DB_ROOT_PASSWORD:` a password for the root user *(only for MySQL)*
+ `DB_PORT:` use `3306` for mysql or `5432` for postgres. This value is used for the metabase container.
+ `DB_OUTSIDE_VOLUME:` a name for the database volume. Defaults to `db-data`. If you change this you'll have to modify the `volumes` section in the `docker-compose` file.
+ `DB_INSIDE_VOLUME:` use `/var/lib/mysql` for mysql or `/var/lib/postgresql/data` for postgres. This values are used by the official images inside the container.