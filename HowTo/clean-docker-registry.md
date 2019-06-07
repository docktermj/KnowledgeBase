# Clean docker-registry

To clean a docker repository, `docker rmi ...` is used.
These instructions are for cleaning a docker registry.

## Delete repository

1. :pencil2: Set environment variables.
   Example:

    ```console
    export DOCKER_ACCOUNT=docktermj
    export DOCKER_REPOSITORY=test
    ```

1. Remove docker images.
   Example:

    ```console
    sudo rm -rf /var/lib/docker-registry/docker/registry/v2/repositories/${DOCKER_ACCOUNT}/${DOCKER_REPOSITORY}
    ```

1. Clean docker metadata.  Example:

    ```console
    sudo docker-registry garbage-collect /etc/docker/registry/config.yml
    ```

1. Restart `docker-registry`.
   Example:

    ```console
    sudo systemctl restart docker-registry
    ```

## Delete account

1. :pencil2: Set environment variables.
   Example:

    ```console
    export DOCKER_ACCOUNT=docktermj
    ```

1. Remove docker images.  Example:

    ```console
    sudo rm -rf /var/lib/docker-registry/docker/registry/v2/repositories/${DOCKER_ACCOUNT}
    ```

1. Clean docker metadata.
   Example:

    ```console
    sudo docker-registry garbage-collect /etc/docker/registry/config.yml
    ```

## Delete all

1. Remove docker images.
   Example:

    ```console
    sudo rm -rf /var/lib/docker-registry/docker/registry/v2/repositories/*
    ```

1. Clean docker metadata.
   Example:

    ```console
    sudo docker-registry garbage-collect /etc/docker/registry/config.yml
    ```
