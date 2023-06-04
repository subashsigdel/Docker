-----
## To create and run docker 

docker run hello-world

-----
### To pull docker image
docker pull "imageName"

-----
### To see docker version  
docker version

-----
### basic docker commands 

docker run hello-world ls <-list out the folders of helloworld container
docker run hello-world sh 
docker ps <-to see running container
docker ps --all <-to sell all running and stopped container
docker stop "containerId" <-stop running container
docker create "ContainerName" <-To create ne docker container
docker start -a "hash string given by docker create"
docker logs "containerId" <-To see container hoistory
docker kill "containerID" <-To kill container
docker exec -i-t "containerID" sh <- To run command in container

------------------------------

Remove a container upon exiting
If you know when you’re creating a container that you won’t want to keep it around once you’re done, you can run docker run --rm to automatically delete it when 
it exits:
----------
Run and Remove:
----------
docker run --rm image_name

---------------

### Docker provides a single command that will clean up any resources — images, containers, volumes, and networks — that are dangling (not tagged or 
associated with a container):
---------------
docker system prune

-----

## To additionally remove any stopped containers and all unused images (not just dangling images), add the -a flag to the command:
-----

docker system prune -a

-----

### Use the docker images command with the -a flag to locate the ID of the images you want to remove. This will show you every image, including intermediate image layers. When you’ve located the images you want to delete, you can pass their ID or tag to docker rmi:
-----
## List:

docker images -a

## Remove:

docker rmi Image Image

-----

## Docker images consist of multiple layers. Dangling images are layers that have no relationship to any tagged images. They no longer serve a purpose and consume disk space. They can be located by adding the filter flag -f with a value of dangling=true to the docker images command. When you’re sure you want to delete them, you can use the docker image prune command:

-----

## List:

docker images -f dangling=true

## Remove:

docker image prune

-----

## Remove one or more specific containersUse the docker ps command with the -a flag to locate the name or ID of the containers you want to remove:
-----
## List:

docker ps -a


## Remove:

docker rm ID_or_Name ID_or_Name


-----
## Remove all exited containers
## You can locate containers using docker ps -a and filter them by their status: created, restarting, running, paused, or exited. To review the list of exited containers, use the -f flag to filter based on status. When you’ve verified you want to remove those containers, use -q to pass the IDs to the docker rm command:
-----
## List:

docker ps -a -f status=exited

## Remove:

docker rm $(docker ps -a -f status=exited -q)


-----
## Removing Volumes
## Remove one or more specific volumes - Docker 1.9 and later
## Use the docker volume ls command to locate the volume name or names you wish to delete. Then you can remove one or more volumes with the docker volume rm command:
-----
## List:

docker volume ls

## Remove:

docker volume rm volume_name volume_name


-----
