## Notes to build, run and manage docker

### Build image
`docker build -t ubuntu:zonation .`

### Run container
`docker run -it -v /Users/uyuni/repos:/home/rstudio/repos -e PASSWORD=PASSWORD=<insert_pass> -d -p 8787:8787 --name inla 2dc3950fedaa`

`docker run -it -v /Users/uyuni/repos:/home/rstudio/repos -d --name zonation e790b66bac1e`

`docker run -it -v ~/repos/zonation/:/home/zon_tools -d --name ztools ubuntu:zonation`

### Pull docker image from Docker Hub
In this case pulling the `uyuni` image from my personal docker hub `cmzambranat`
`docker pull cmzambranat/uyuni`

#### Run docker-compose
This will run the docker container with settings specified in the `docker-compose.yml`. The `-d` flag is to run docker in detached mode.

`docker-compose up -d`

### Tips
Use --rm together with `docker build` to remove intermediary images during the build process.

To run bash in a container
`docker exec -it zonation bash`

### List docker images
`docker image ls`

### Remove dangling/untagged images
`docker images -q --filter dangling=true | xargs docker rmi`

### List docker containers
`docker ps`
Add `-a` flag to list all stopped containers
`docker ps -a`

### Stop container
`docker stop [CONTAINER ID]`

### Remove all stopped containers
`docker ps -aq --no-trunc -f status=exited | xargs docker rm`

### circleci

1. Create job in `circleci`
2. Link to github repo
3. Import variables



