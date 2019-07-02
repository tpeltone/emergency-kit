# Docker Commands

List running containers:

```bash
docker ps
```

List all containers:

```bash
docker ps -a
```

Remove containers:

```bash
docker rm <CONTAINER ID>
```

List the most recently created/available images on my system:

```bash
docker images
```

List all available images on my system:

```bash
docker images -a
```

How to remove docker images:

```bash
docker rmi <IMAGE ID>
```

Remove images according to a pattern:

* List

 ```bash
 docker images -a |  grep "pattern"
 ```

* Remove

 ```bash
docker images -a | grep "pattern" | awk '{print $3}' | xargs docker rmi
 ```

Stop & Remove All Docker Containers:

```bash
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
```

Docker provides a single command that will clean up any resources — images, containers, volumes, and networks — that are dangling (not associated with a container):

```bash
docker system prune
```

To additionally remove any stopped containers and all unused images (not just dangling images), add the -a flag to the command:

```bash
docker system prune -a
```

Links:

[How To Remove Docker Images, Containers, and Volumes](https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes)

[How to Remove Docker Images and Containers](https://tecadmin.net/remove-docker-images-and-containers/)
