# VMWare Workstation

[Software](README.md#V) > VMWare Workstation

## Versions

1. [VMware Workstation 16](vmware-workstation-16.md)
1. [VMware Workstation 14](vmware-workstation-14.md)
1. [VMware Workstation 12](vmware-workstation-12.md)
1. [VMware Workstation 10](vmware-workstation-10.md)

## Etc

1. [VMware images](vmware-images.md)

## Tips

1. See [How-to Install VMware Player in Ubuntu 12.04 Precise Pangolin (Linux Kernel 3.2)](http://debianhelp.wordpress.com/2012/06/08/how-to-install-vmware-player-in-ubuntu-12-04/ )
1. [How-To: Get VMware Virtual Machines to Use Three or More Monitors](http://blog.timmattison.com/archives/2011/07/07/how-to-get-vmware-virtual-machines-to-use-three-or-more-monitors/ )
    1. For 3 [Dell U2410](../hardware/dell-u2410.md) monitors: svga.vramSize=40000000
1. Archiving a clone
    1. Make a clone
        1. VM > Manage > Clone...
        1. `cd /path/to/ubuntu-14.04-desktop-amd64-updated`
        1. `tar -cvzf ubuntu-14.04-desktop-amd64-updated *`
1. VMware Tools
    1. `/usr/bin/vmware-toolbox-cmd`
    1. To enable advanced X features (e.g., guest resolution fit, drag and drop, and file and text copy/paste), you will need to do one (or more) of the following:
        1. Manually start /usr/bin/vmware-user
        1. Log out and log back into your desktop session; and,
        1. Restart your X session.
