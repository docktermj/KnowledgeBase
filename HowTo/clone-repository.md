# Clone repository

## Set environment variables for repository

1. :pencil2: If not already set, set environment variables for organization/account and the name of the repository.
   Example:

    ```console
    export GIT_ACCOUNT=docktermj
    export GIT_REPOSITORY=name-of-repository
    ```

1. Synthesize environment variables.

    ```console
    export GIT_ACCOUNT_DIR=~/${GIT_ACCOUNT}.git
    export GIT_REPOSITORY_DIR="${GIT_ACCOUNT_DIR}/${GIT_REPOSITORY}"
    ```

## URL for non-development

1. Use this example for anonymous access.

    ```console
    export GIT_REPOSITORY_URL="https://github.com/${GIT_ACCOUNT}/${GIT_REPOSITORY}.git"
    ```

## URL for development

1. Use this example if you want to log in with your GitHub credentials.

    ```console
    export GIT_REPOSITORY_URL="git@github.com:${GIT_ACCOUNT}/${GIT_REPOSITORY}.git"
    ```

## Perform clone repository

1. On Linux, get repository.

    ```console
    mkdir --parents ${GIT_ACCOUNT_DIR}
    cd  ${GIT_ACCOUNT_DIR}
    git clone  --recurse-submodules ${GIT_REPOSITORY_URL}
    ```

1. On macOS, get repository.

    ```console
    mkdir -p ${GIT_ACCOUNT_DIR}
    cd  ${GIT_ACCOUNT_DIR}
    git clone --recurse-submodules ${GIT_REPOSITORY_URL}
    ```
