## Docker

```bash
# Delete all stopped containers
docker ps --filter "status=exited" | awk '{print $1}' | xargs --no-run-if-empty docker rm
# Delete AWS Ecr Untagged
aws ecr describe-repositories --output text | awk '{print $5}' | while read line; do  aws ecr list-images --repository-name $line --filter tagStatus=UNTAGGED --query 'imageIds[*]' --output text | while read imageId; do aws ecr batch-delete-image --repository-name $line --image-ids imageDigest=$imageId; done; done
```

```bash
docker images # display all the images
```


```bash
docker ps -a # display all the containers
```

```bash
docker build -t name path # build image
docker build -t cool-engine . # your image name is called cool-engine your path is current directory
docker build -t engine --build-arg NAME=something . # passing build args to build
```

```bash
docker rmi tag/name # remove image with either tag or name
docker rmi $(docker images --filter "dangling=true" -q --no-trunc) # remove untagged images
```

```bash
docker run -d --name ContainerName ImageName # run container in dameon
docker run -d -p 80:8080 ImageName # run container with port 80 being external and 8080 internally
docker run -d -e API_KEY='nwegn3t5' # run container with environmental variable
docker run -d -e E1='e1' -e E2='e2' # multiple environmental variable
docker run -d -p 80:80 -e FOO='bar' --name ContainerName ImageName # everything
docker run -v /host/directory:/container/directory # mount volume
```

```bash
docker exec id/ContainerName ls # run command inside container
docker exec id/ContainerName cd /usr/path # latter is commands
```

```bash
docker stop id/ContainerName # stop a running container
docker rm id/ContainerName # remove a stoped container

docker stop $(docker ps -a -q) # stop all running container
docker rm $(docker ps -a -q) # remove all running container
```

```bash
docker login # log into docker hub
sudo yum install -y docker # install on AWS
```

```bash
docker pull user-name/docker-name # pull container from docker hub
docker pull user-name/docker-name:tag # with tag
```

```bash
docker stats # get docker cpu/memory stats
```

```bash
docker logs containerId # to get logs for that container
```

#### Simple Rebuild Script
```bash
# Use it like this ./rebuild.sh name 80:80
#chmod +x rebuild.sh
#./rebuild.sh

NAME=$1
PORT=$2

# Clean and Remove all
docker stop $NAME
docker rm $NAME
docker rmi $NAME

# Build and Run
docker build -t $NAME .
docker run -d -p $2 --name $NAME $NAME
```
