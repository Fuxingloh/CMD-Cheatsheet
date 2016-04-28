## Docker

```bash
docker images # display all the images
```


```bash
docker ps -a # display all the containers
```

```bash
docker build -t name path # build image
docker build -t cool-engine .
```

```bash
docker rmi tag/name # remove image with either tag or name
```

```bash
docker run -d --name ContainerName ImageName # run container in dameon
docker run -d -p 80:8080 ImageName # run container with port 80 being external and 8080 internally
docker run -d -e API_KEY='nwegn3t5' # run container with environmental variable
docker run -d -e E1='e1' -e E2='e2' # multiple environmental variable
docker run -d -p 80:80 -e FOO='bar' --name ContainerName ImageName # everything
```

```bash
docker exec id/ContainerName ls # run command inside container
docker exec id/ContainerName cd /usr/path # latter is commands
```

```bash
docker stop id/ContainerName # stop a running container
docker rm id/ContainerName # remove a stoped container

```bash
docker stop $(docker ps -a -q) # stop all running
```

```bash
```

```bash
```

```bash
```

```bash
```
