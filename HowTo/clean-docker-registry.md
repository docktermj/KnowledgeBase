# Clean docker-registry

To clean a docker repository, `docker rmi ...` is used.
These instructions are for cleaning a docker registry.

## Delete

1. Remove docker images.  Example:

    ```console
    sudo rm -rf /var/lib/docker-registry/docker/registry/v2/repositories/*
    ```

1. Clean docker metadata.  Example:

    ```console
    sudo docker-registry garbage-collect /etc/docker/registry/config.yml
    ```
