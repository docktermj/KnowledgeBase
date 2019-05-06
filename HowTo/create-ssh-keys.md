# Create ssh keys

## Ubuntu

### Create files

1. :pencil2: Set environment variables.  Example:

    ```console
    export SSH_EMAIL_ADDRESS="me@example.com"
    export SSH_DIRECTORY=${HOME}/my-ssh
    ```

1. :pencil2: Optional: Set key name.   If not set, it defaults to `id_rsa`.  Example:

    ```console
    export SSH_KEY_NAME="my-key"
    ```

1. Generate key file and certificate.  Example:

    ```console
    mkdir -p ${SSH_DIRECTORY}
    cd ${SSH_DIRECTORY}

    ssh-keygen \
        -b 4096 \
        -C "${SSH_EMAIL_ADDRESS}" \
        -f ${SSH_DIRECTORY}/${SSH_KEY_NAME:-id_rsa} \
        -N '' \
        -t rsa
    ```
