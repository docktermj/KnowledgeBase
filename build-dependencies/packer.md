# Build dependencies for Packer

## Packer

- [Installation](https://www.packer.io/intro/getting-started/install.html)

```console
$ packer version
Packer v1.2.5
```

## Vagrant

- [Installation](https://www.vagrantup.com/docs/installation/)

```console
$ vagrant -v
Vagrant 2.1.2
```

## VirtualBox

- [Installation](https://www.virtualbox.org/)

```console
$ vboxmanage --version
5.1.38_Ubuntur122592
```

## VirtualBox Guest Additions

### Ubuntu

```console
sudo apt-get install -y virtualbox-guest-additions-iso
sudo vagrant plugin install vagrant-vbguest
```

### CentOS

```console
vagrant plugin install vagrant-vbguest
```

