# Basic docker

- docker search: search for a docker image e.g docker search redis
- docker ps: ps of dockers
- docker run -d <image>: run docker image detach
- docker inspect <name|container id>: inspect docker process
- docker run -d --name <name> -p <host-port>:<continer-port> <image>: map ports
- docker run -d --name <name> -p <port> <image>: map to random port
- docker run -it <image>: run interactive tty
- docker build -t <build-directory>  i.e docker build -t webserver-image:v1 . : build with current directory
- docker images: show images