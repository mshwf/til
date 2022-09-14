## Commands

`run <image name | image id>` runs a container from an image, downloads it if it's not found, if it's a web server, it will run in attached mode.
```
run [name:tag]	> run a container with a specific tag  
	-d	> runs a container in a detached (background) mode (you can keep working in console)
	-it	>'i'nteractive 't'erminal mode (uses the current terminal for the running container process in interactive way)
	--name (string)> assign a name to the container
pull		> pulls an image from a repository (DockerHub)
ps 		> lists all running containers
	-a	> lists all containers (running or stopped)
stop [name|id]>	> stop a container by its name or id
rm [name|id]>	> kills/remove container
images>		> lists all images
version		> lists version matrix

`logs [container_id | name]` show logs of a running container (useful for containers running in background 'detached mode')

`docker images -f dangling=true -q` lists dangling images (<none> images)

stop $(docker ps -a -q)	> stops all containers

save -o [path for generated tar file] [image name] > save docker image as tar file
docker load -i [path to image tar file] > load docker image from tar file [https://stackoverflow.com/a/23938978/6197785]

docker-compose up> run all containers defined in the docker-compose file
docker-compose down> stop all containers defined in the docker-compose file


container data is lost after removing container (https://youtu.be/fqMOX6JJhGo?t=2408)

Docker build example (on the solution root):
	docker build -f WebFrontEnd/Dockerfile -t myfrontend --rm .

docker run -it --rm -p 80:4100 -p 443:4101 -e ASPNETCORE_HTTPS_PORT=https://+:4101 -e ASPNETCORE_URLS=http://+:4100 webapplication1
docker run -it --rm -p 4100:80 -p 4101:443 -e ASPNETCORE_HTTPS_PORT=https://+:4101 -e ASPNETCORE_URLS=http://+:4100 webapplication1

The correct simple way: 
	docker run -dp 4122:80 webapplication1
Move out the logs folder:
	docker run -v C:/GETLogs/FromDockerTest:C:/GETLogs/DockerTest -dp 4122:80 webapplication1


If you are attempting to add a container to an existing network that no longer exists, then you can use:
	docker-compose up --force-recreate
	
Get environment variables:
	docker exec container env

```
