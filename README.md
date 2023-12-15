# Docker + ReactJS tutorial: Development to Production workflow + multi-stage builds + docker compose

## Docker

`Dockerfile`

### Build Docker image

`$ docker build -t react-image .`

`$ docker build {-t|--tag} react-image {-f|--file} Docker.dev`

#### List docker images

`$ docker image ls`

#### Remove docker image

`$ docker image rm {image-name|image-id}`

### Run Docker container

`$ docker run -d -v ${pwd}/app:/app:ro -p 3000:3000 --name {container-name} {image-name|image-id}`

`-d` detached mode
`-v` volume; `:ro` read only
`-p` port mapping
`--name` container name
`-e` environment variable
`--env-file {./.env}` environment file

### Stop & remove Docker constainer

`$ docker rm {container-name} -f`


### Connect to Docker container

`$ docker exec -it container-name {sh|bash}`

#### Prod build

`$ docker build -f Dockerfile.prod -t docker-image-prod`

#### Prod run

`$ docker run -d --env-file ./.env -p 8080:80 --name react-app-prod docker-image-prod`

## Docker Compose

`docker-compose.yaml`

### Docker Compose Start

`$ docker-compose up -d [--build]`

Option:
`--build` To build or rebuild image

### Docker Compose Shutdown

`$ docker-compose down`

## YouTube

### Sanjeev Thiyagarajan

Docker + ReactJS tutorial: Development to Production workflow + multi-stage builds + docker compose