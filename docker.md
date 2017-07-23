docker:
=======

Basic:
------
 - Test your Docker installation by running the following: `docker run hello-world`
 - The pull command fetches the busybox image from the Docker registry and saves it to our system: `docker pull busybox`
 - command to see a list of all images on your system `docker images`
 - run a Docker container based on this image: `docker run busybox`
 
run basic redis container:
--------------------------
 - Firs get the image: `docker pull redis`
 - start a redis instance: `docker run --name some-redis -d redis` #This image includes EXPOSE 6379 (the redis port)
 - or start with persistent storage: `docker run --name some-redis -d redis redis-server --appendonly yes`
 - connect to it via via redis-cli `docker run -it --link some-redis:redis --rm redis redis-cli -h redis -p 6379` #it will prompt `redis:6379>`
 - from cli run the commmand:
 ```bash
 redis:6379> set docker awesome
 redis:6379> get docker
 redis:6379> exit
 ```
 - see the running containers: `docker ps`
 - stop the running container: `docker stop <container id>` #find the "container id" using "docker ps" command

resources:
----------
* Windows Containers on Windows 10 - https://docs.microsoft.com/en-us/virtualization/windowscontainers/quick-start/quick-start-windows-10
* Run IIS + ASP.NET on Windows 10 with Docker - http://blog.alexellis.io/run-iis-asp-net-on-windows-10-with-docker/
* An Overview of .NET and Containers - http://blog.alexellis.io/docker-dotnet-containers/
* Very simple tutorial - https://prakhar.me/docker-curriculum/