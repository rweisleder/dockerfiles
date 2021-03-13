FROM postgres:12.1-alpine

# Store database inside the container
# see https://nickjanetakis.com/blog/docker-tip-79-saving-a-postgres-database-in-a-docker-image
ENV PGDATA=/data

# Download Sakila from jOOQ
ADD \
    --chown=postgres:postgres \
    https://github.com/rweisleder/jOOQ/raw/main/jOOQ-examples/Sakila/postgres-sakila-db/postgres-sakila-schema.sql \
    /docker-entrypoint-initdb.d/01_create_schema.sql
ADD \
    --chown=postgres:postgres \
    https://github.com/rweisleder/jOOQ/raw/main/jOOQ-examples/Sakila/postgres-sakila-db/postgres-sakila-insert-data.sql \
    /docker-entrypoint-initdb.d/02_insert_data.sql
