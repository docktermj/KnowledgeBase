# Create self-signed certificate

## Ubuntu

### Create files

1. :pencil2: Set environment variables.  Example:

    ```console
    export CERTIFICATE_NAME=my-certificate
    export CERTIFICATE_DAYS=3650
    ```

1. Generate key file and certificate.  Example:

    ```console
    openssl req \
      -x509 \
      -nodes \
      -days ${CERTIFICATE_DAYS} \
      -newkey rsa:4096 \
      -keyout ~/${CERTIFICATE_NAME}.key \
      -out ~/${CERTIFICATE_NAME}.pem
    ```

### Move files

1. Place `.key` file.  Example:

    ```console
    sudo cp ~/${CERTIFICATE_NAME}.key /etc/ssl/private/
    sudo chown root:ssl-cert /etc/ssl/private/${CERTIFICATE_NAME}.key
    sudo chmod 640 /etc/ssl/private/${CERTIFICATE_NAME}.key
    ```

1. Place `.pem` file.  Example:

    ```console  
    sudo cp ~/${CERTIFICATE_NAME}.pem /etc/ssl/certs/
    sudo chmod 644 /etc/ssl/certs/${CERTIFICATE_NAME}.pem
    ```

### Remove exposed files

After any testing, it is safe to remove the files from the user's home directory.

1. Delete temporary `.key` and `.pem` files.  Example:

    ```console
    rm ~/${CERTIFICATE_NAME}.key
    rm ~/${CERTIFICATE_NAME}.pem
    ```

### Remove all files

:warning:  This removes the files.  There is no recovery.

1. Delete `.key` and `.pem` files.  Example:

    ```console
    sudo rm /etc/ssl/private/${CERTIFICATE_NAME}.key
    sudo rm /etc/ssl/certs/${CERTIFICATE_NAME}.pem
    ```
