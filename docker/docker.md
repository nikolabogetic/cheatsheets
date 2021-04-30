# Docker

```bash
docker run -it --entrypoint bash ubuntu
```

```
docker
docker ps
docker info
docker --version
```

List images and containers
```
docker images
docker image ls
docker container ls
```

Pull and run (no tag means latest)
```
docker search nginx
docker pull nginx
docker run nginx:latest
```
Parameters
```
# Detached
docker run -d nginx:latest

# Forward host port to container port. Repeat -p for multiple ports
docker run -d -p 8080:80 nginx:latest

# Give a name
docker run --name nikola -d -p 8080:80 nginx:latest

# Mount a volume (ro means read only)
docker run --name some-nginx -v /some/content:/usr/share/nginx/html:ro -d nginx:latest

# Mount volumes from a running container
docker run --name some-nginx-2 --volumes-from some-nginx -d -p 8081:80 nginx:latest

# Restart on fail. Another policy is always
docker run -d --name restart-example --restart=on-failure:3 scrapbook/docker-restart-example
```


Build and tag
```
docker build -t nikola:latest .
docker tag nikola:latest nikola:1.1
```
Start, stop, inspect, logs
```
docker stop <id or name>
docker start <id or name>


docker inspect <id or name>
docker logs <id or name>
```

Other
```
# Show all containers (including stopped)
docker ps -a

# Delete container
docker rm <id or name>

# Delete image
docker rmi <image>

# Delete all containers
docker rm -f $(docker ps -aq)

# Get to shell
docker exec -it nikola /bin/bash

# Stats
docker top <id or name>
docker stats <id or name> [--no-stream]
docker ps -q | xargs docker stats

# Save
docker save redis:3.2.11-alpine > redis.tar
```

Registry
```
docker tag nikola:latest nikolabogetic/nikola:latest
docker push nikolabogetic/nikola:latest
```
Ports
```
# Run on a specific IP
docker run -d --name redisHostPort -p 127.0.0.1:6379:6379 redis:latest

# Run on a random port
docker run -d --name redisDynamic -p 6379 redis:latest
docker port redisDynamic 6379
```

Data containers
```
docker create -v /config --name dataContainer busybox
docker cp config.conf dataContainer:/config/
docker export dataContainer > dataContainer.tar
docker import dataContainer.tar
```

Linked containers
```
docker run -d --name redis-server redis

docker run --link redis-server:redis alpine env
# --link <other container>[:<alias>]
# This will run the env command and terminate, not permanent
```
Networks
```
docker network create backend-network
docker run -d --name=redis --net=backend-network redis

docker network create frontend-network
docker network connect frontend-network redis

docker network disconnect frontend-network redis
```
