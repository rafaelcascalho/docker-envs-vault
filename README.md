# Infra setups

This repository have multiple docker compose files for infra setup of local projects or even environments with docker and docker compose.

## Prerequisites

To use this setup files for components such as databases, just [install docker](https://docs.docker.com/engine/install/ubuntu/) and [docker compose](https://docs.docker.com/compose/install/)

## Setup

To get components up an running just copy the `docker-compose.*.yml` file you want, then run the command below

```sh
$ docker-compose up
```

## UI for Components

Each file have the system components is setup to go up with its UI component (ex: PGadmin for PostgreSQL).

## Infra Components (and clients)

### Databases

- Postgres
- MySQL
- MongoDB

### Cache

- Redis

### Queues

- Kakfa
- Rabbitmq

## Tracing

- Jaeguer

## Auth

- Keycloak
