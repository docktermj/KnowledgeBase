# goclipse

[GoClipse](https://marketplace.eclipse.org/content/goclipse) in Eclipse Marketplace.

## Install

1. Install [Eclipse 4.8](eclipse-4.8) or later
1. Eclipse > Help > Eclipse Marketplace...
1. Find: "Go"
1. Choose: "GoClipse"

## Configuration

### Linux Configuration

1. Eclipse > Window > Preferences > Go
1. Go
    1. Go installation:
        1. Directory: /usr/local/go
    1. Eclipse GOPATH
        1. [x] Use same value as the GOPATH environment variable
        1. [x] Also add project location to GOPATH, if it's not contained there already.
1. Build Console
1. Editor
    1. Typing
        1. Indentation
            1. Indentation mode: Spaces
1. Tools
    1. gocode:
        1. Executable: /usr/local/go/bin/go
    1. [guru](guru.md):
        1. Executable:
    1. godef:
        1. Executable:
    1. gofmt:
        1. [x] Use default location (from Go installation).
        1. Executable: /usr/local/go/bin/gofmt
        1. [ ] Format automatically on editor save

### macOS Configuration

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
        1. Executable: /usr/local/go/bin/go
    1. guru:
        1. Executable:
    1. godef:
        1. Executable:
    1. gofmt:
        1. :ballot_box_with_check: Use default location (from Go installation).
        1. Executable: /usr/local/go/bin/gofmt
        1. :black_square_button: Format automatically on editor save