# WebSVN

## Download

1. Example:

    ```console
    curl -X GET --output /tmp/websvn-master.zip https://codeload.github.com/websvnphp/websvn/zip/master
    ```

## Installation

1. As root, example:

    ```console
    cd /var/www/html
    unzip /tmp/websvn-master.zip
    mv websvn-master websvn
    ```

1. [Install Subversion and Websvn on Ubuntu 16.04](https://gotechnies.com/install-subversion-websvn-ubuntu-16-04/)

### Access control

1. `htpasswd -/home/svn/conf/passwd michael`

1. Obsolete:
    1. /usr/share/websvn/include/distconfig.php
    1. /etc/websvn/config.php
    1. `mkdir /home/svn/conf`
    1. `cp /home/svn/v01.00.conf/* /home/svn/conf/`
    1. $config->useAuthenticationFile('/path/to/accessfile');

## Configuration

## References

1. [Install Subversion and Websvn on Ubuntu 16.04](https://gotechnies.com/install-subversion-websvn-ubuntu-16-04/)
1. [WebSvn access control](http://blesseddlo.wordpress.com/2010/04/09/websvn-user-access-control/)
1. [Web interface to Subversion: WebSVN - access control](http://daemon-notes.com/articles/web/websvn)
