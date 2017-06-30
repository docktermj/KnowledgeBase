
1. Create CentOS Packer image.
   1. https://github.com/docktermj/packer-centos-eclipse-cpp
1. Bring up guest virtual machine in VMware or Vagrant.
1. Copy SSH credentials to guest virtual machine.
   1. On host machine terminal:
```console
scp ~/.ssh/id_rsa vagrant@nn.nn.nn.nn:.ssh/id_rsa
```
1. Install Go.
   1. On guest virtual machine terminal:
```console
sudo yum -y install \
    git \
    tar \
    wget

export GO_VERSION=1.8.3

wget https://storage.googleapis.com/golang/go${GO_VERSION}.linux-amd64.tar.gz
sudo tar -C /usr/local/ -xzf go${GO_VERSION}.linux-amd64.tar.gz

export GOPATH="${HOME}/go"
export PATH="${PATH}:${GOPATH}/bin:/usr/local/go/bin"
```
1. Install dependencies.
   1. On guest virtual machine terminal:
```console
go get -u github.com/nsf/gocode
go get github.com/rogpeppe/godef
go get golang.org/x/tools/cmd/guru
```
1. Find locations of files for configuring Eclipse.
   1. On guest virtual machine terminal:
```console
export X_GOCODE=$(readlink -f $(which gocode))
export X_GURU=$(readlink -f $(which guru))
export X_GODEF=$(readlink -f $(which godef))
export X_GOFMT=$(readlink -f $(which gofmt))
export X_GOPATH=$(readlink -f ${HOME}/go)
```
1. Add Eclipse "GoClips" plugins.
   1. Eclipse > Help > Eclipse Marketplace...
   1. *Find:* GoClips
   1. In "GoClips", click "Install" button.
1. Configure GoClips plugin
   1. Eclipse > Window > Preferences
      1. Preferences > Go > Tools
         1. **gocode:** value of ${X_GOCODE}
         1. **guru:** value of ${X_GURU}
         1. **godef:** value of ${X_GODEF}
         1. **gofmt:** value of ${X_GOFMT}
            1. Uncheck :white_medium_square: Use default location
         1. Click "Apply" button.
      1. Preferences > Go
         1. **Go Installation:** /usr/local/go
         1. Eclipse GOPATH
            1. Uncheck :white_medium_square: Use same value as the GOPATH environment variable
            1. `:${X_GOPATH}`  Note: colon prefix is important!
               1. Example: `:/home/vagrant/go`
         1. Click "Apply" button.
      1. Preferences > Go > Editor > Typing
         1. Indentation
            1. **Indentation mode:** Spaces
            1. **Displayed tab size:** 4
            1. **Indentation size:** 4
         1. Click "Apply" button
      1. Click "OK" button.


## Running Eclipse remotely

```console
 ssh -X -f vagrant@nn.nn.nn.nn eclipse
```
