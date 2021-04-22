# goclipse

[Software](README.md#g) > goclipse

## Documentation

1. [GitHub](http://goclipse.github.io/)
1. [Eclipse marketplace](https://marketplace.eclipse.org/content/goclipse)

## Installation

Use [Eclipse Marketplace](eclipse-marketplace.md)

1. Eclipse > Help > Eclipse Marketplace...
    1. Search for "GoClipse"

## Configuration

### Configuration on Linux

1. Eclipse > Window > Preferences > Go
1. Go
    1. Go installation:
        1. Directory: `/usr/local/go`
    1. Eclipse GOPATH
        1. [x] Use same value as the GOPATH environment variable
        1. [x] Also add project location to GOPATH, if it's not contained there already.
1. Build Console
1. Editor
    1. Typing
        1. Indentation
            1. Indentation mode: Spaces
1. Tools
    1. [gocode](gocode.md):
        1. Executable: `/usr/local/go/bin/go`
    1. [guru](guru.md):
        1. Executable: `/usr/local/go/bin/guru`
    1. [godef](godef.md):
        1. Executable: `/usr/local/go/bin/godef`
    1. [gofmt](gofmt.md):
        1. :ballot_box_with_check:  Use default location (from Go installation).
        1. Executable: `/usr/local/go/bin/gofmt`
        1. :black_square_button: Format automatically on editor save

### Configuration on macOS

1. Eclipse > Eclipse > Preferences... > Go
1. Go
    1. Go installation:
        1. Directory: /usr/local/go
    1. Eclipse GOPATH
        1. :ballot_box_with_check: Use same value as the GOPATH environment variable
        1. :ballot_box_with_check: Also add project location to GOPATH, if it's not contained there already.
1. Build Console
1. Editor
    1. Typing
        1. Indentation
            1. Indentation mode: Spaces
1. Tools
    1. gocode:
        1. Executable: `/usr/local/go/bin/go`
    1. guru:
        1. Executable: `/usr/local/go/bin/guru`
    1. godef:
        1. Executable: `/usr/local/go/bin/godef`
    1. gofmt:
        1. :ballot_box_with_check: Use default location (from Go installation).
        1. Executable: `/usr/local/go/bin/gofmt`
        1. :black_square_button: Format automatically on editor save

## References

1. [Install GoClipse](https://github.com/GoClipse/goclipse/blob/latest/documentation/Installation.md#installation)
    1. [README](https://github.com/GoClipse/goclipse/blob/master/README.md)
