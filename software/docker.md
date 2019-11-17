# docker

[Software](README.md#D) > docker

## Versions

1. [docker-ce](docker-ce.md)
1. [docker-ee](docker-ee.md)

## Installation

1. [docker-ce](docker-ce.md#installation)
1. [docker-ee](docker-ee.md#installation)

## Commands

### docker command line

1. [Using the Docker command line](https://docs.docker.com/engine/reference/commandline/cli/)
1. [docker commands](https://docs.docker.com/edge/engine/reference/commandline/docker/)

    ```console
    sudo docker
    ```

### docker build

1. Open a new terminal to an existing docker container.

    ```console
    sudo docker build -t dockter/docker-alpine:3.1 .
    ```

    where "-t" is the tag of the image.
    Don't forget the final period. (".")

### docker exec

1. Open a new terminal to an existing docker container.

    ```console
    sudo docker exec -it {ubuntu_bash} bash
    ```

### docker ps

1. List running docker containers.

    ```console
    sudo docker ps
    ```

1. List all docker containers.

    ```console
    sudo docker ps -a
    ```

### docker push

Push to [dockter/docker-alpine](https://hub.docker.com/r/dockter/docker-alpine/)

```console
sudo docker push dockter/docker-alpine:3.1
```

### docker rm

1. Remove all images that have exited (as seen in "sudo docker ps -a")

    ```console
    sudo docker rm $(sudo docker ps -qa --no-trunc --filter "status=exited")
    ```

    ```console
    sudo docker rm -v $(sudo docker ps -qa --no-trunc --filter "status=exited")
    ```

### docker run

1. Run a single command.

    ```console
    sudo docker run ubuntu:14.04 /bin/echo 'Hello world'
    ```

1. Run an interactive shell.

    ```console
    sudo docker run -t -i ubuntu:14.04 /bin/bash
    ```

### docker stop

1. Stop a docker container.

    ```console
    sudo docker stop image_name
    ```

## Tips

1. FROM
    1. For small footprint use:
        1. FROM alpine:3.5
        1. FROM python:3.4-alpine

1. Images

    1 redis:alpine

1. Static binaries

    1. When using "alpine", the binaries need to be static.  Example:

    ```console
    go build --tags netgo --ldflags '-extldflags "-lm -lstdc++ -static"'
    ```

### Clean up

1. [Docker - How to cleanup (unused) resources](https://gist.github.com/bastman/5b57ddb3c11942094f8d0a97d461b430)

    ```console
    docker rmi $(docker images | grep "local/" | awk '/ / { print $3 }')
    docker rmi $(docker images | grep "nubix/" | awk '/ / { print $3 }')
    ```

### Security

1. [Why we don't let non-root users run Docker in CentOS, Fedora, or RHEL](http://www.projectatomic.io/blog/2015/08/why-we-dont-let-non-root-users-run-docker-in-centos-fedora-or-rhel/)

## References

1.[Ubuntu Trusty 14.04 (LTS) (64-bit)](http://docs.docker.com/installation/ubuntulinux/#ubuntu-trusty-1404-lts-64-bit)

1. [documentation](http://docs.docker.com )
    1.[Command Line Reference](https://docs.docker.com/engine/reference/commandline/cli/)
    1.[Dockerfile reference](https://docs.docker.com/engine/reference/builder/)
1. [Docker Hub](https://hub.docker.com/)
1. [How To Remove Docker Images, Containers, and Volumes](https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes)
1. [docker-compose](docker-compose.md)
