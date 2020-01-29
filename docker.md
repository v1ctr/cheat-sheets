# Docker Cheat Sheet

## Docker CLI (docker)

### Building a Container
    docker build -t <repository-name>:<tag> .
* The `-t` or `--tag` argument gives a name and tag to the container image.
* The `latest` tag is usually used for the most up-to-date version of a container image.
* The dot at the end of the `build` command sets the current directory as the top-level directory during the build.

### Listing images on local system
    docker images

### Removing image on local system
    docker rmi <image-id>
    
### Running a Container
    docker run --name <container-name> -d -p <host-port>:<container-port> <repository-name>:<tag>
* The `--name` argument gives a name to the container.
* The `-d` or `--detach` argument runs the container in the background.
* The `-p` or `--publish` argument maps the host-port to the port inside the container.

Environment Variables

    - e <key>=<value>
* The `-e` or `--env` argument sets environment variables that are going to exist in the context of the container.

### Listing running Container
    docker ps
    
### Stopping a Container
    docker stop <container-id>
### Removing a Container
    docker rm <container-id>
### Removing all Containers (only if stopped)
    docker rm $(docker ps -a -q)
* The `-a` or `--all` argument to `docker ps` shows all containers (not just running).
* The `-q` or `--quiet` argument to `docker ps` only displays the numeric IDs.

### Combine Stopping and Removing
    docker rm -f <container-id>

### Inspecting a Running Container
Open a shell session without interrupting the container:
    
    docker exec -it <container-id> sh
* The `-i` or `--interactive` argument keeps the STDIN open even if the container is not attached.
* The `-t` or `--tty` argument allocates a pseudo-TTY.

## Docker Compose CLI (docker-compose)
### Running a Container
    docker-compose up -d --build
* The `--build` argument indicates that a build step should run before launching the application.

### Listing all running Application Containers
    docker-compose ps
    
### Stopping the Application
    docker-compose down
    
### Combine Stopping and Removing
    docker-compose rm --stop --force

### Restart single container
    docker-compose restart <container-name>

### Monitoring the log stream
    docker-compose logs -f
* The `-f` or `--follow` argument follows the log output.

## Useful Images
### PostgreSQL
Running the postgres container

    docker run --name postgres -e POSTGRES_PASSWORD=<postgres-password> -d -p 5432:5432 postgres

Entering the postgres container

    docker exec -it postgres psql -U postgres
    
### pgAdmin
    docker run -p 8040:80 -e 'PGADMIN_DEFAULT_EMAIL=<email>' -e 'PGADMIN_DEFAULT_PASSWORD=<password>' -d dpage/pgadmin4

### adminer
    docker run --name adminer -d -p 8080:8080 adminer