# Go

1. [Source repository](https://github.com/golang/go)

## Installation

### Installation for Ubuntu

1. [Getting Started](https://golang.org/doc/install)
1. :pencil2: Example:

    ```console
    export GO_VERSION=1.13.4

    wget https://dl.google.com/go/go${GO_VERSION}.linux-amd64.tar.gz
    sudo tar -C /usr/local -xzf ./go${GO_VERSION}.linux-amd64.tar.gz
    ```

## Configuration

1. Environment variables.
   Example:

    ```console
    export GOPATH="${HOME}/go"

    mkdir -p ${GOPATH}
    mkdir ${GOPATH}/bin
    mkdir ${GOPATH}/pkg
    mkdir ${GOPATH}/src

    export PATH="${PATH}:/usr/local/go/bin:${GOPATH}/bin"
    ```

1. Persist environment variables.
   Example:

    ```console
    cat <<EOT >> ~/.bashrc

    # Set environment variables for go language
    export GOPATH="${HOME}/go"
    export GOROOT=/usr/local/go
    export PATH=$PATH:${GOROOT}/bin:${GOPATH}/bin
    EOT
    ```

## Tools

Install the following tools:

1. [GoCode](gocode.md#installation)
1. [GoDef](godef.md#installation)
1. [guru](guru.md#installation)

## Eclipse

1. See [GoClipse](goclipse.md)

## Standards

1. [Go Documentation](https://golang.org/doc)
    1. [How to Write Go Code](https://golang.org/doc/code.html)
    1. [Effective Go](https://golang.org/doc/effective_go.html)
1. [github.com/golang-standards/project-layout](https://github.com/golang-standards/project-layout)

## Awesome

1. [Go projects](https://github.com/golang/go/wiki/Projects)
1. [Software Design Patterns](https://github.com/tmrts/go-patterns)

## GoClipse tutorials

1. [A Tour of Go](https://tour.golang.org)
1. [Google Go Programming in Eclipse](http://www.tutorialsavvy.com/2013/04/google-go-programming-in-eclipse.html/)

## Go packages

1. [Projects](https://github.com/golang/go/wiki/Projects)
    1. [Awesome Go](https://github.com/avelino/awesome-go) - A curated list of awesome Go frameworks, libraries and software.
1. [Go Plugin System over RPC](https://github.com/hashicorp/go-plugin)
    1. [GoDoc](https://godoc.org/github.com/hashicorp/go-plugin)

## Go modules

1. [Using Go Modules](https://blog.golang.org/using-go-modules)
1. [Simple Go project layout with modules](https://eli.thegreenplace.net/2019/simple-go-project-layout-with-modules/)
1. [Modules](https://github.com/golang/go/wiki/Modules)

## Go plugins

1. [Go Execution Modes by Ian Lance Taylor](http://bit.ly/1l7VFsL) - Discusses upcoming go "standard" plugin package.
1. go-plugin
    1. Examples:
        1. [x](https://github.com/hashicorp/go-plugin/issues/11)
            1. [x](https://github.com/hashicorp/terraform/tree/master/plugin)
            1. [x](https://github.com/hashicorp/terraform/tree/master/builtin)
            1. [x](https://github.com/hashicorp/otto-example-app-plugin)
            1. [x](https://github.com/hashicorp/otto/tree/v0.2.0)

## Go examples

1. [Subclassing](https://play.golang.org/p/1uvs6MORHK)

## Video

1. [Writing, building, installing, and testing Go code](https://www.youtube.com/watch?v=XCsL89YtqCs)
1. [Go: a simple programming environment](https://vimeo.com/53221558)
1. [Go: the cool parts](http://oredev.org/2015/sessions/go-the-cool-parts)

## Documentation

1. [Command line options](https://golang.org/cmd/go/)

## References

1. [Home page](https://golang.org)
    1. [Go Documentation](https://golang.org/doc)
        1. [Getting Started](https://golang.org/doc/install)
        1. [Effective Go](https://golang.org/doc/effective_go.html)
    1. pkg
        1. [Stringer](http://golang.org/pkg/fmt/#Stringer)
    1. src
        1. [Example](https://golang.org/src/go/doc/example.go)
1. [tour.golang.org](https://tour.golang.org)
1. [Go's declaration syntax](https://blog.golang.org/gos-declaration-syntax)
    1. [Go environment variables](https://golang.org/cmd/go/#hdr-Environment_variables)
