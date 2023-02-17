Simple bank Resources

## My SQL generate

https://dbdiagram.io/d/63ef363a296d97641d81b1be

## Install use Docker + Postgres - Start a Docker instance

```
docker run --name postgres15 -p 5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=kien6034 -d postgres:15-alpine
```

Flag: -p 5432:5432 tell that docker to create a bridge between our localhost network and container network

- Access to docker and its console

```
docker exec -it docker_name sql -U root
```

- To start a docker container

```
docker start containername
```

- To stop a docker container

```
docker stop container_name
```

## Write and run database migration

### Install golang migrate

```
brew install golang-migrate
```

- Start sh shell docker apline

```
docker exec -it postgres15 /bin/sh
```

- Migrate the db

```
 migrate -path db/migration -database "postgresql://root:kien6034@localhost:5432/simple_bank?sslmode=disable" -verbose up
```
