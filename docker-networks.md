# Docker Networks

First create a network with CLI with "docker network create backend-network". Then connect the new container with "docker run -d --redis --net=backend-network redis"

## Explore the network

When containers attempt to access other containers via a well-known name, such as Redis, the DNS server will return the IP address of the correct Container. In this case, the fully qualified name of Redis will be redis.backend-network.
``` bash
$docker run --net=backend-network alpine ping -c1 redis
```