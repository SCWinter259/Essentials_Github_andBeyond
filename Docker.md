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

Build a container:

```sh
docker build -t <user_name>/<container_name>:<version> <location>

# example
docker build -t scwinter/peakcv-server:1.0 .
```

Run a container:

```sh
docker run -p <local_port>:<docker_port> <container_name>

# example
docker run -p 3001:8080 peakvc-server
```
