# Docker

## Commands

### List running containers

```bash
docker ps
```

### List all containers

```bash
docker ps -a
```

### Remove containers

```bash
docker rm <CONTAINER ID>
```

### List the most recently created/available images on my system

```bash
docker images
```

### List all available images on my system

```bash
docker images -a
```

### How to remove docker images

```bash
docker rmi <IMAGE ID>
```

### Remove images according to a pattern

* List

 ```bash
 docker images -a |  grep "pattern"
 ```

* Remove

 ```bash
docker images -a | grep "pattern" | awk '{print $3}' | xargs docker rmi
 ```

### Stop & Remove All Docker Containers

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

### Browse in a running docker container

```bash
# "sudo su - root" on the server to run this
docker exec -it <container name> /bin/bash
```

### How to fix docker: Got permission denied while trying to connect to the Docker daemon socket

According to the official Docker docs [here](https://docs.docker.com/install/linux/linux-postinstall/#manage-docker-as-a-non-root-user)

You need to do the following:

To create the docker group and add your user:

Create the docker group.
sudo groupadd docker
Add your user to the docker group.

```bash
sudo usermod -aG docker ${USER}
```

You would need to loog out and log back in so that your group membership is re-evaluated or type the following command:

```bash
su -s ${USER}
```

Verify that you can run docker commands without sudo.

```bash
docker run hello-world
```

This command downloads a test image and runs it in a container. When the container runs, it prints an informational message and exits.

If you initially ran Docker CLI commands using sudo before adding your user to the docker group, you may see the following error, which indicates that your ~/.docker/ directory was created with incorrect permissions due to the sudo commands.

```bash
WARNING: Error loading config file: /home/user/.docker/config.json -
stat /home/user/.docker/config.json: permission denied
```

To fix this problem, either remove the ~/.docker/ directory (it is recreated automatically, but any custom settings are lost), or change its ownership and permissions using the following commands:

```bash
sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "$HOME/.docker" -R
```

Restart the docker daemon to get things working:

```bash
sudo systemctl restart docker
```

## docker-compose commands

### Log

```bash
docker-compose logs -f
```
