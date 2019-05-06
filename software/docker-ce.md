# docker community edition (docker-ce)

[Software](README.md#D) > [docker](docker.md) > docker-ce

## Installation

### Ubuntu 14.04 (LTS) installation

1. Example:

    ```console
    #!/bin/bash

    lsb_release -a
    # No LSB modules are available.
    # Distributor ID: Ubuntu
    # Description:    Ubuntu 14.04.1 LTS
    # Release:    14.04
    # Codename:   trusty

    uname -a
    # Linux ubuntu 3.13.0-39-generic #66-Ubuntu SMP Tue Oct 28 13:30:27 UTC 2014 x86_64 x86_64 x86_64 GNU/Linux

    # Install docker
    sudo apt-get update
    sudo apt-get install docker.io
    source /etc/bash_completion.d/docker.io
    docker --version
    # Docker version 1.0.1, build 990021a

    # Get latest version
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 36A1D7869245C8950F966E92D8576A8BA88D21E9
    sudo sh -c "echo deb https://get.docker.com/ubuntu docker main > /etc/apt/sources.list.d/docker.list"
    sudo apt-get update
    sudo apt-get install lxc-docker
    docker --version
    # Docker version 1.3.1, build 4e9bbfa

    # test
    sudo docker run -i -t ubuntu /bin/bash
    ```

1. To run docker without being sudo:

    ```console
    sudo chmod 777 /var/run/docker.sock
    ```

### macOS installation

1. Install Chocolatey from [chocolatey.org](https://chocolatey.org/)

    ```console
    choco install -y docker-for-windows
    ```

1. [Get started with Docker on Windows using Chocolatey](https://stefanscherer.github.io/get-started-with-docker-on-windows-using-chocolatey/)

### Windows 10 on VMware Workstation installation

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