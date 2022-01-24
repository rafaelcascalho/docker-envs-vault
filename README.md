# Infra setups

This repository have multiple files required to dockerize your project, and/or to get tools or system components with a single command using docker-compose.

## Prerequisites

To use this setup files for components such as databases, just [install docker](https://docs.docker.com/engine/install/ubuntu/) and [docker compose](https://docs.docker.com/compose/install/)

## Setup

To get components up an running just copy the files in the required folder. Some tools only required a `docker-compose.*.yml` file.

- `.dockerignore`
- `Dockerfile`
- `docker-compose.*.yml`

## UI for infra Components

Each file have the system components is setup to go up with its UI component (ex: PGadmin for PostgreSQL).

## Dockerize your project

The Dockerfiles follow good practices such as multi stage builds, which is why you must precise the desired target for the build.

To get it up and running fast, just follow the steps below:

1. Copy the files from the folder referencing the context of your project (ex: nodejs)

   - `.dockerignore`
   - `Dockerfile`
   - `docker-compose.*.yml`

2. Now, just run the `docker-compose` command with the expected stage image

   ```sh
   docker-compose up --build DESIRED_TARGET
   ```

Check the list of supported contexts right now

- [NodeJs](nodejs/)
- [Python](python/#) (comming soon)
- [React](react/#) (comming soon)
- [Flutter](flutter/#) (comming soon)

## Infra Components (with clients) and tools

1. Copy the files from the folder referencing the context of your project (ex: nodejs)

   - `.dockerignore`
   - `Dockerfile`
   - `docker-compose.*.yml`

2. Now, just run the `docker-compose` command with the expected stage image

   ```sh
   docker-compose up
   ```

Check the list below of infra components and tools

### Databases

- [Postgres](infra/docker-compose.postgres.db.yml)
- [MySQL](infra/docker-compose.mysql.db.yml)
- [MongoDB](infra/docker-compose.mongo.db.yml)

### Cache

- [Redis](infra/docker-compose.redis.yml)

### Queues

- [Kakfa](infra/docker-compose.kafka.q.yml)
- [Rabbitmq](infra/docker-compose.rabbitmq.q.yml)

### Tracing

- [Jaeguer](infra/docker-compose.jaeguer.yml)
- [New Relic](tools/#) (comming soon)

## Tools

- [Keycloak](tools/docker-compose.keycloak.yml)
