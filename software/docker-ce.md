# docker community edition (docker-ce)

[Software](README.md#D) > [docker](docker.md) > docker-ce

## Installation

### Installation on Centos

1. [Official instructions](https://docs.docker.com/install/linux/docker-ce/centos/)
1. [Digital Ocean instructions](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-centos-7)
   Synopsis:

    ```centos
    sudo yum check-update
    curl -fsSL https://get.docker.com/ | sh
    sudo systemctl start docker
    ```

### Installation on Ubuntu 24.04

1. [Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)

1. Download Docker's official GPG key

    ```console
    sudo install -m 0755 -d /etc/apt/keyrings
    sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    sudo chmod a+r /etc/apt/keyrings/docker.asc
    ```

    ```console
    echo \
        "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
        $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
        sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt-get update
    ```

1. Install docker

    ```console
     sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
    ```

1.

### Installation on macOS

1. Install Chocolatey from [chocolatey.org](https://chocolatey.org/)

    ```console
    choco install -y docker-for-windows
    ```

1. [Get started with Docker on Windows using Chocolatey](https://stefanscherer.github.io/get-started-with-docker-on-windows-using-chocolatey/)

### Installation on Windows 10 on VMware Workstation

1. VMware > {VMware image} > Settings > Processors
    1.Virtualization Engine > Preferred mode: Intel VT-x or AMD-V

1. As administrator, in command prompt:

    ```console
    .\"Docker for Windows Installer.exe"
    ```

1. As administrator, in command prompt:

    ```console
    cd %SYSTEMROOT%\System32
    MOFCOMP WindowsVirtualization.V2.mof
    ```

1. Create a virtual switch named "VirtualSwitch".

    ```console
    docker-machine create --driver hyperv --hyperv-virtual-switch VirtualSwitch default
    ```

1. Reference: [Issue:  Docker failed to start on windows 10](https://github.com/docker/for-win/issues/748#issuecomment-323468016)

1. [Fix](https://github.com/docker/for-win/issues/1825#issuecomment-433719346)

    ```console
    cd "C:\Program Files\Docker\Docker
    ./dockerCli.exec -SwitchDaemon
    ```

1. [Enable Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v#enable-hyper-v-using-powershell)

### Installation test

1. Docker version on Ubuntu.
   Example:

    ```console
    $ sudo docker version
    Client:
     Version:           18.09.7
     API version:       1.39
     Go version:        go1.10.1
     Git commit:        2d0083d
     Built:             Fri Aug 16 14:20:06 2019
     OS/Arch:           linux/amd64
     Experimental:      false

    Server:
     Engine:
      Version:          18.09.7
      API version:      1.39 (minimum version 1.12)
      Go version:       go1.10.1
      Git commit:       2d0083d
      Built:            Wed Aug 14 19:41:23 2019
      OS/Arch:          linux/amd64
      Experimental:     false
    ```
