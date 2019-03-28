# Docker Networks

First create a network with CLI with "docker network create backend-network". Then connect the new container with "docker run -d --redis --net=backend-network redis"

## Explore the network

When containers attempt to access other containers via a well-known name, such as Redis, the DNS server will return the IP address of the correct Container. In this case, the fully qualified name of Redis will be redis.backend-network.
``` bash
$docker run --net=backend-network alpine ping -c1 redis
```

## Connecting two networks

Docker supports multiple networks and containers being attached to more than one network at a time.

```bash
$docker network create frontend-network
```

When using the connect command it is possible to attach existing containers to the network.
```bash
$docker network connect frontend-network redis
```

When we launch the web server, given it's attached to the same network it will be able to communicate with our Redis instance.

```bash
$docker run -d -p 3000:3000 --net=frontend-network katacoda/redis-node-docker-example 
```

## Connect Container with Alias



The following command will connect our Redis instance to the frontend-network with the alias of db.

```bash
docker network create frontend-network2
docker network connect --alias db frontend-network2 redis
```
## Disconnect
With our networks created, we can use the CLI to explore the details.

The following command will list all the networks on our host.
``` bash
$docker network ls
```
We can then explore the network to see which containers are attached and their IP addresses.
``` bash
$docker network inspect frontend-network
```
The following command disconnects the redis container from the frontend-network.
``` bash
$docker network disconnect frontend-network redis
```