# Minishift

## Installation

### Installation on Ubuntu

1. Visit [github.com/minishift/minishift/releases](https://github.com/minishift/minishift/releases) to determine latest release.

1. :pencil2: Identify the version of `minishift`.
   Example:

    ```console
    export MINISHIFT_TGZ=minishift-1.34.1-linux-amd64
    ```

1. Download `minishift-M.mm.P-linux-amd64.tgz`.
   Example:

    ```console
    wget \
      --output-document ~/Downloads/${MINISHIFT_TGZ}.tgz \
      https://github.com/minishift/minishift/releases/download/v1.34.1/${MINISHIFT_TGZ}.tgz
    ```

1. Extract.
   Example:

    ```console
    tar -xvz \
      --directory ~ \
      --file ~/Downloads/${MINISHIFT_TGZ}.tgz
    ```

1. Move binary to directory in $PATH.
   Example:

    ```console
    sudo mv ~/${MINISHIFT_TGZ}/minishift /usr/local/bin
    ```

1. :Warning: Make sure `MINISHIFT_TGZ` is set.
   Delete extracted directory.
   Example:

    ```console
    rm -rf ~/${MINISHIFT_TGZ}/*
    ```

## Commands

### xxx

## References

1. [Openshift with minishift setup](http://raman-kumar.blogspot.com/2019/08/openshift-okd-cluster-with-minishift.html)
1. [Command reference](https://docs.okd.io/latest/minishift/command-ref/minishift.html)
    1. [minishift start](https://docs.okd.io/latest/minishift/command-ref/minishift_start.html)
1. Installation
    1. [Install (Openshift) minishift in Ubuntu 18.04](https://medium.com/@kasun.dsilva/install-openshift-minishift-in-ubuntu-18-04-fe0760d5a54d)
