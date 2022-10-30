# VMWare Workstation 16

[Software](README.md#V) > [VMWare Workstation](vmware-workstation.md) > VMWare Workstation 14

## Kernel change

1. When the kernel changes, VMware has an error like:

    ```console
    Could not open /dev/vmmon: No such file or directory.
    Please make sure that the kernel module `vmmon' is loaded.
    Failed to initialize monitor device.
    ```console

1. To fix, as root:

    ```console
    wget https://github.com/mkubecek/vmware-host-modules/archive/workstation-16.2.4.tar.gz
    tar -xzf workstation-16.2.4.tar.gz
    cd vmware-host-modules-workstation-16.2.4
    make
    sudo make install
    cp vmmon.o /lib/modules/`uname -r`/kernel/drivers/misc/vmmon.ko
    cp vmnet.o /lib/modules/`uname -r`/kernel/drivers/misc/vmnet.ko
    depmod -a
    /etc/init.d/vmware restart
    ```
