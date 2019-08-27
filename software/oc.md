# oc

## Installation

### Installation on Ubuntu

1. Visit [github.com/openshift/origin/releases](https://github.com/openshift/origin/releases) to determine latest release.

1. :pencil2: Identify the version of `oc`.
   Example:

    ```console
    export OC_VERSION=v3.11.0
    export OC_SHA=0cbc58b
    export OC_TGZ=openshift-origin-client-tools-${OC_VERSION}-${OC_SHA}-linux-64bit
    ```

1. Download `openshift-origin-client-tools-M.mm.P-linux-64bit.tar.gz`.
   Example:

    ```console
    curl -X GET \
      --location \
      --output ~/Downloads/${OC_TGZ}.tgz \
      https://github.com/openshift/origin/releases/download/${OC_VERSION}/openshift-origin-client-tools-${OC_VERSION}-${OC_SHA}-linux-64bit.tar.gz
    ```

1. Extract.
   Example:

    ```console
    tar -xvz \
      --directory ~ \
      --file ~/Downloads/${OC_TGZ}.tgz
    ```

1. Move binary to directory in $PATH.
   Example:

    ```console
    sudo mv ~/${OC_TGZ}/oc /usr/local/bin
    ```

1. :Warning: Make sure `OC_TGZ` is set.
   Delete extracted directory.
   Example:

    ```console
    rm -rf ~/${OC_TGZ}/*
    ```

## Commands

## References
