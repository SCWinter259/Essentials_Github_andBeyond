# Docker

To add your local user to Docker:

```sh
sudo usermod -aG docker $USER
```

Login to a user group:

```sh
newgrp <group_name>
```

Check all groups:

```sh
groups
```

Check all containers:

```sh
docker ps -a
```

Build a container (this command already tagged the container):

```sh
docker build -t <container_name>:<tag> <location>

# example
docker build -t scwinter/peakcv-server:1.0 .
```

If your container is not yet tagged, here is how to make a tag:

```sh
docker tag <local_image_name>:<tag> <dockerhub_username>/<repo_name>:<tag>

# example
docker tag my-backend:latest caspernguyen/my-backend:latest
```

Run a container:

```sh
docker run -p <local_port>:<docker_port> <container_name>

# example
docker run -p 3001:8080 scwinter/peakcv-server:1.0
```

To stop a background container:

```sh
docker stop <container_name>
```

Login on command line:

```sh
docker login
```

Push an image onto Docker Hub:

```sh
docker push <dockerhub_username>/<repo_name>:<tag>

# example
docker push caspernguyen/my-backend:latest
```

