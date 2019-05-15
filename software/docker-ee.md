# docker-ee

[Software](README.md#D) > [docker](docker.md) > docker-ee

## Installation

### Installation on ???

1. [store.docker.com/procurement](https://store.docker.com/procurement)
    1. Enter activation key
1. Username > My Content
    1. Docker Enterprise > [Setup](https://hub.docker.com/u/senzing/content/sub-63e3629a-88e0-4993-9588-0d5e53b9e94e)
    1. [Get Docker EE for Ubuntu](https://docs.docker.com/install/linux/docker-ee/ubuntu/)
    1. My-Content URL.  Example:

        ```console
        export DOCKER_USERNAME=dockter
        echo "https://hub.docker.com/u/${DOCKER_USERNAME}/content"
        ```

1. Download "Resources > License Key"

1. Choose correct acccount.

1. :pencil2: Set environment variables.  Example:

    ```console
    # Find local ip address
    ifconfig

    set LOCAL_IP_ADDRESS=127.0.0.1
    ```

1. [Install license](https://docs.docker.com/ee/end-to-end-install/)

    ```console
    sudo docker container run \
      --rm \
      -it \
      --name ucp \
      -v /var/run/docker.sock:/var/run/docker.sock \
      docker/ucp:3.1.6 install \
        --host-address ${LOCAL_IP_ADDRESS} \
        --interactive
    ```

### Installation on Ubuntu

1. [Get Docker EE for Ubuntu](https://docs.docker.com/install/linux/docker-ee/ubuntu/)

1. [Post-installation steps for Linux](https://docs.docker.com/install/linux/linux-postinstall/)
