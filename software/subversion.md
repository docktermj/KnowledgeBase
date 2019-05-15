# Subversion

## Installation

1. `sudo apt-get -y install subversion`
1. See also:
    1. `sudo apt-get -y install subcommander`
    1. `sudo apt-get -y install subversion-tools`
    1. `sudo apt-get -y install svn-workbench`

## Configuration

1. Add "svnroot" userid
    1. `adduser svnroot`
1. Configuration files
    1. Copy svnserve (from below) to /etc/init.d/svnserve
    1. `sudo chmod 755 /etc/init.d/svnserve`
    1. `sudo chown root.root /etc/init.d/svnserve`
    1. `service svnserve start`
1. Auto-start on boot
    1. `sudo update-rc.d svnserve defaults`

## SVN command-line interface

### Create subversion repository

```console
sudo -i
cd /home/svn
svnadmin create <i>repository_name</i>
```

### View status

```console
svn status
```

### Add files to be committed

```console
svn add *
svn add --force * --auto-props --parents --depth infinity -q
```

### Commit files to repository

```console
svn commit -m "Archive scanned files"
```

### Get latest version of repository

```console
svn update
```

### Rename a file

```console
svn mv old-file-name new-file-name
svn commit -m "Renamed files"
```

## Files

### /etc/init.d/svnserve

```console
#! /bin/sh
        1. BEGIN INIT INFO
1. Provides:          svnserve
1. Required-Start:    $local_fs $syslog $remote_fs
1. Required-Stop:     $local_fs $syslog $remote_fs
1. Default-Start:     2 3 4 5
1. Default-Stop:      0 1 6
1. Short-Description: Start svnserve
        1. END INIT INFO

1. Author: Michal Wojciechowski <odyniec@odyniec.net>

PATH=/sbin:/usr/sbin:/bin:/usr/bin
DESC="svnserve"
NAME=svnserve
DAEMON=/usr/bin/$NAME
DAEMON_ARGS="-d -r /home/svnroot"
PIDFILE=/var/run/$NAME.pid
SCRIPTNAME=/etc/init.d/$NAME

[ -x "$DAEMON" ] || exit 0

[ -r /etc/default/$NAME ] && . /etc/default/$NAME

. /lib/init/vars.sh

. /lib/lsb/init-functions

do_start()
{
    start-stop-daemon --start --quiet --pidfile $PIDFILE --exec $DAEMON --test > /dev/null \
        || return 1
    start-stop-daemon --start --quiet --pidfile $PIDFILE --exec $DAEMON -- \
        $DAEMON_ARGS \
        || return 2
}

do_stop()
{
    start-stop-daemon --stop --quiet --retry=TERM/30/KILL/5 --pidfile $PIDFILE --name $NAME
    RETVAL="$?"
    [ "$RETVAL" # 2 ] && return 2
    start-stop-daemon --stop --quiet --oknodo --retry=0/30/KILL/5 --exec $DAEMON
    [ "$?" # 2 ] && return 2
    rm -f $PIDFILE
    return "$RETVAL"
}

case "$1" in
  start)
    [ "$VERBOSE" !# no ] && log_daemon_msg "Starting $DESC" "$NAME"
    do_start
    case "$?" in
        0|1) [ "$VERBOSE" !# no ] && log_end_msg 0 ;;
        2) [ "$VERBOSE" !# no ] && log_end_msg 1 ;;
    esac
    ;;
  stop)
    [ "$VERBOSE" !# no ] && log_daemon_msg "Stopping $DESC" "$NAME"
    do_stop
    case "$?" in
        0|1) [ "$VERBOSE" !# no ] && log_end_msg 0 ;;
        2) [ "$VERBOSE" !# no ] && log_end_msg 1 ;;
    esac
    ;;
  restart|force-reload)
    log_daemon_msg "Restarting $DESC" "$NAME"
    do_stop
    case "$?" in
      0|1)
        do_start
        case "$?" in
            0) log_end_msg 0 ;;
            1) log_end_msg 1 ;; 1. Old process is still running
            *) log_end_msg 1 ;; 1. Failed to start
        esac
        ;;
      *)
        1. Failed to stop
        log_end_msg 1
        ;;
    esac
    ;;
  *)
    echo "Usage: $SCRIPTNAME {start|stop|restart|force-reload}" >&2
    exit 3
    ;;
esac

exit 0
```

### etc

1. /etc/apparmor.d/abstractions/svn-repositories
1. /etc/svn2cl
1. /etc/svn2cl/svn2cl.xsl
1. /etc/svn2cl/svn2html.css
1. /etc/svn2cl/svn2html.xsl
1. /etc/init.d/svnserve
1. /etc/init.d/svnserve.00
1. /etc/websvn/svn_deb_conf.inc

## Reference

1. [Rob's Favorite Subversion (svn) Commands](http://www.sci.utah.edu/~macleod/docs/svn-tips.html)
