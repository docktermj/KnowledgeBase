# Installing and configuring Eclipse

1. Visit [eclipse.org/neon](https://eclipse.org/neon/)

## Download and run installer

1. Visit [Eclipse packages](https://eclipse.org/downloads/eclipse-packages/)
1. Download the "Eclipse Installer" (In this example, download to `~/Downloads`)
1. Extract installer.  Example:

    ```console
    tar -xzvf ~/Downloads/eclipse-inst-linux64.tar.gz -C ~
    ```

1. Run installer. Example:

    ```console
    ~/eclipse-installer/eclipse-inst
    ```

## Install Eclipse

In "EclipseInstaller":

1. Choose "Eclipse IDE for C/C++ Developers"

## Create a desktop shortcut

This work in Ubuntu. Unknown if it works in other Linux distributions.

1. Create the *.desktop file.

    ```console
    cat <<EOT > ~/Desktop/cpp-eclipse.desktop
    #!/usr/bin/env xdg-open
    [Desktop Entry]
    Version=1.0
    Type=Application
    Terminal=false
    Icon[en_US]=eclipse
    Name[en_US]=Eclipse for C++
    Exec=${HOME}/eclipse/cpp-neon/eclipse/eclipse
    Name=CPP-eclipse
    Icon=eclipse
    EOT
    ```

1. Make file executable

    ```console
    chmod 755 ~/Desktop/cpp-eclipse.desktop 
    ```

1. An Eclipse icon labeled "Eclipse for C++" should appear on your desktop.

## References

1. [How to install Eclipse using its installer](http://askubuntu.com/questions/695382/how-to-install-eclipse-using-its-installer)



