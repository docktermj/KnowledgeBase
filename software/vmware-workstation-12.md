# VMWare Workstation 12

[Software](README.md#V) > [VMWare Workstation](vmware-workstation.md) > VMWare Workstation 12

## Download

1. [Download](https://my.vmware.com/group/vmware/info/slug/desktop_end_user_computing/vmware_workstation_pro/12_0)

## Installation

1. [Install Workstation Pro on a Linux Host](https://docs.vmware.com/en/VMware-Workstation-Pro/12.0/com.vmware.ws.using.doc/GUID-1F5B1F14-A586-4A56-83FA-2E7D8333D5CA.html)
1. [VMware License keys](https://my.vmware.com/group/vmware/my-licenses#/prodFilter)

### Ubuntu 18.04 specific

1. [VMWare does not start](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1715552)
    1. [Comment #26](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1715552/comments/26)

### Patch procedure

Based on:

1. [Linux / VMWare – Failed to get gcc information](https://cloudpro.zone/index.php/2017/08/30/vmware-failed-gcc-information/)
1. Comment #36 of [VMWare does not start](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1715552)
    1. [Comment #26](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1715552/comments/26)

1. Install VMware Workstation 12.5.9

    ```console
    sudo ./VMware-Workstation-Full-12.5.9-7535481.x86_64.bundle
    ````

1. From [Comment #26](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1715552/comments/26)

    ```console
    cd ~
    git clone https://github.com/mkubecek/vmware-host-modules.git
    cd ~/vmware-host-modules
    git checkout workstation-12.5.9
    ```

1. From [INSTALL - First method](https://github.com/mkubecek/vmware-host-modules/blob/workstation-12.5.9/INSTALL)

    ```console
    wget https://github.com/mkubecek/vmware-host-modules/archive/workstation-12.5.9.tar.gz
    tar -xzf workstation-12.5.9.tar.gz
    cd vmware-host-modules-workstation-12.5.9
    make
    sudo make install
    ```

1. From [Linux / VMWare – Failed to get gcc information](https://cloudpro.zone/index.php/2017/08/30/vmware-failed-gcc-information/)

    ```console
    cd /usr/lib/vmware/modules/source
    tar xvf vmnet.tar
    tar xvf vmmon.tar
    cd vmnet-only
    make
    cd ../vmmon-only
    make
    cd ..
    cp vmmon.o /lib/modules/`uname -r`/kernel/drivers/misc/vmmon.ko
    cp vmnet.o /lib/modules/`uname -r`/kernel/drivers/misc/vmnet.ko
    depmod -a
    /etc/init.d/vmware restart
    ```

1. From [Comment #26](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1715552/comments/26)

    ```console
    cd /usr/lib/vmware/lib/libz.so.1
    sudo mv libz.so.1 libz.so.1.old
    sudo ln -s /lib/x86_64-linux-gnu/libz.so.1 .
    sudo depmod -a
    sudo /etc/init.d/vmware restart
    ```

### Kernel change

1. When the kernel changes, VMware has an error like:

    ```console
    Could not open /dev/vmmon: No such file or directory.
    Please make sure that the kernel module `vmmon' is loaded.
    Failed to initialize monitor device.
    ```console

1. To fix, as root:

    ```console
    wget https://github.com/mkubecek/vmware-host-modules/archive/workstation-12.5.9.tar.gz
    tar -xzf workstation-12.5.9.tar.gz
    cd vmware-host-modules-workstation-12.5.9
    make
    sudo make install
    cp vmmon.o /lib/modules/`uname -r`/kernel/drivers/misc/vmmon.ko
    cp vmnet.o /lib/modules/`uname -r`/kernel/drivers/misc/vmnet.ko
    depmod -a
    /etc/init.d/vmware restart
    ```

1. References:
    1. To recompile kernel parts,
       see [VMware kernel module: a compatible version of gcc was not found](https://unix.stackexchange.com/questions/310637/vmware-kernel-module-a-compatible-version-of-gcc-was-not-found)
    1. ["Cannot open /dev/vmmon: No such file or directory" error when powering on a VM (2146460)](https://kb.vmware.com/s/article/2146460)

## Configuration

## References

1. [Using VMware Workstation Pro](https://docs.vmware.com/en/VMware-Workstation-Pro/12.0/com.vmware.ws.using.doc/GUID-0EE752F8-C159-487A-9159-FE1F646EE4CA.html)
    1. [Install Workstation Pro on a Linux Host](https://docs.vmware.com/en/VMware-Workstation-Pro/12.0/com.vmware.ws.using.doc/GUID-1F5B1F14-A586-4A56-83FA-2E7D8333D5CA.html)
    1. [Using the vmware Command](https://docs.vmware.com/en/VMware-Workstation-Pro/12.0/com.vmware.ws.using.doc/GUID-AE43508D-A717-485D-B991-2CB9136E54D7.html)
        1. [Run the vmware Command](https://docs.vmware.com/en/VMware-Workstation-Pro/12.0/com.vmware.ws.using.doc/GUID-DA203314-F153-4F1F-8FCF-A7700530943D.html)
        1. [vmware Command Options](https://docs.vmware.com/en/VMware-Workstation-Pro/12.0/com.vmware.ws.using.doc/GUID-7369457F-FE1D-40FE-97B6-B29CA4916CCD.html)
1. [Linux / VMWare – Failed to get gcc information](https://cloudpro.zone/index.php/2017/08/30/vmware-failed-gcc-information/)
