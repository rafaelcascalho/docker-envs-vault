# Docker envs vault

This repository is intended to serve as a vault to easily dockerize your envs just by copying the files under the folder of your specific tech stack. Beyond that, part of a dockerized environment is to use the other system components (databases, cache systems, message brokers, monitors, etc) with docker as well; but those, many times do not need a Dockerfile of their own, and therefore, a simple docker-compose written correctly already helps to get the service(s) up with
all of its system component(s) easily with a single command: `docker-compose up`.

## Advanced Usage

For certain scenarios such as monorepo cases, where you have multiple Dockerfiles and probably a single docker-compose file, 

## Prerequisites

To use the system components files for something like a database, just [install docker](https://docs.docker.com/engine/install/ubuntu/) and [docker compose](https://docs.docker.com/compose/install/) and follow the instructions below.

## UI for System Components

Intending to be a one stop place, every system component, under the [infra folder](/infra/), comes along with an UI, to create easily visualization of the
components while they're running.

> Ex: pgadmin for PostgreqSQL

## Dockerize your project

The Dockerfiles follow good practices such as multi stage builds, which is why you must precise the desired target for the build.

To get it up and running fast, just follow the steps below:

1. Copy the files from the folder referencing the tech stack of your project (ex: nodejs) to the root of your own project

   - `.dockerignore`
   - `Dockerfile`
   - `docker-compose.*.yml`

2. Now, just run the `docker-compose` command with the expected stage image

   ```sh
   docker-compose up --build DESIRED_TARGET
   ```

Check the list of supported tech stacks right now

- [NodeJs](nodejs/)
  - [TS](nodejs/ts/)
  - [NestJs + TS](nodejs/nestjs-ts/)
- [Python](python/#) (comming soon)
- [React](react/#) (comming soon)
- [Flutter](flutter/#) (comming soon)

## Infra Components (with clients) and tools

1. Copy the files from the folder referencing the tech stack of your project (ex: nodejs)

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
