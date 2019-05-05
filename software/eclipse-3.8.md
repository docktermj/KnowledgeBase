# Eclipse 3.8 - Juno

[Software](README.md#E) > [eclipse](eclipse.md) > Eclipse 3.8

## Install

### Ubuntu

1. Example:

    ```console
    #!/bin/bash
    # Eclipse  (Version 3.8 - Juno)
    sudo apt-get -y install eclipse
    # sudo mkdir /root/.eclipse
    # sudo chmod 755 /root/.eclipse
    ```

1. Manual install of plugins

    Update eclipse plugins and platform.

    ```console
    sudo eclipse -clean
    ```

    Eclipse > Help > Clean for Updates

    To find -installIU value, look in Eclipse > Help > Install New Software... > {Choose} > More... > General Information > Identifier

    ```console
    # Eclipse plugins
    sudo eclipse -nosplash \
        -application org.eclipse.equinox.p2.director \
        -repository http://download.eclipse.org/releases/juno/ \
        -installIU org.eclipse.cdt.feature.group/ \
        -installIU org.eclipse.cdt.sdk.feature.group \
        -installIU org.eclipse.datatools.enablement.sdk.feature.feature.group \
        -installIU org.eclipse.datatools.sdk.feature.feature.group \
        -installIU org.eclipse.dltk.rse.feature.group \
        -installIU org.eclipse.egit.feature.group \
        -installIU org.eclipse.jdt.feature.group \
        -installIU org.eclipse.jst.webpageeditor.feature.feature.group \
        -installIU org.eclipse.linuxtools.valgrind.feature.group \
        -installIU org.eclipse.m2e.feature.feature.group \
        -installIU org.eclipse.mylyn.context_feature.feature.group \
        -installIU org.eclipse.mylyn.github.feature.feature.group \
        -installIU org.eclipse.mylyn.ide.ui \
        -installIU org.eclipse.php.sdk.feature.group \
        -installIU org.eclipse.rse.feature.group \
        -installIU org.eclipse.team.svn.feature.group \
        -installIU org.eclipse.team.svn.source.feature.group \
        -installIU org.eclipse.wst.jsdt.feature.feature.group \
        -installIU org.eclipse.wst.web_ui.feature.feature.group \
        -installIU org.eclipse.wst.xml_ui.feature.feature.group

    sudo eclipse -nosplash \
        -application org.eclipse.equinox.p2.director \
        -repository http://download.eclipse.org/tools/cdt/releases/juno/ \
        -installIU org.eclipse.cdt.feature.group

    sudo eclipse -nosplash \
        -application org.eclipse.equinox.p2.director \
        -repository http://download.eclipse.org/linuxtools/update/ \
        -installIU org.eclipse.linuxtools.man.core

    sudo eclipse -nosplash \
        -application org.eclipse.equinox.p2.director \
        -repository http://download.eclipse.org/mpc/juno/ \
        -installIU org.eclipse.epp.mpc.feature.group

    sudo eclipse -nosplash \
        -application org.eclipse.equinox.p2.director \
        -repository http://eclipsesql.sourceforge.net/ \
        -installIU net.sourceforge.sqlexplorer.feature.group

    sudo eclipse -nosplash \
        -application org.eclipse.equinox.p2.director \
        -repository http://andrei.gmxhome.de/eclipse/ \
        -installIU AnyEditTools.feature.group

     sudo eclipse -nosplash \
        -application org.eclipse.equinox.p2.director \
        -repository http://community.polarion.com/projects/subversive/download/eclipse/3.0/juno-site/ \
        -installIU org.polarion.eclipse.team.svn.connector.svnkit17.feature.group

    sudo eclipse -nosplash \
        -application org.eclipse.equinox.p2.director \
        -repository http://www.nodeclipse.org/updates/markdown/ \
        -installIU markdown.editor.feature.feature.group

    # Gets version 3.2.  Need 3.0
    # sudo eclipse -nosplash \
    #     -application org.eclipse.equinox.p2.director \
    #     -repository http://download.eclipse.org/tools/orbit/downloads/drops/R20130118183705/repository/ \
    #     -installIU org.antlr.runtime

    # Eclipse PyDev plugin
    wget "http://pydev.org/pydev_certificate.cer" -O /tmp/pydev_certificate.cer
    sudo keytool -import -v -noprompt -trustcacerts -file /tmp/pydev_certificate.cer -keystore /usr/lib/jvm/java-7-openjdk-amd64/jre/lib/security/cacerts -storepass changeit
    sudo eclipse -nosplash -application org.eclipse.equinox.p2.director -repository http://download.eclipse.org/releases/juno/,http://pydev.org/updates/ -installIU org.python.pydev.feature.feature.group

    # Eclipse Dynamic Languages Toolkit plugins
    sudo eclipse -nosplash \
        -application org.eclipse.equinox.p2.director \
        -repository http://download.eclipse.org/technology/dltk/updates-dev/latest/ \
        -installIU org.eclipse.dltk.core.feature.group \
        -installIU org.eclipse.dltk.core.index.feature.group \
        -installIU org.eclipse.dltk.core.index.sdk.feature.group \
        -installIU org.eclipse.dltk.core.sdk.feature.group \
        -installIU org.eclipse.dltk.debug.ui \
        -installIU org.eclipse.dltk.itcl.feature.group \
        -installIU org.eclipse.dltk.itcl.sdk.feature.group \
        -installIU org.eclipse.dltk.javascript.feature.group \
        -installIU org.eclipse.dltk.javascript.sdk.feature.group \
        -installIU org.eclipse.dltk.mylyn.feature.group \
        -installIU org.eclipse.dltk.mylyn.sdk.feature.group \
        -installIU org.eclipse.dltk.python.feature.group \
        -installIU org.eclipse.dltk.python.sdk.feature.group \
        -installIU org.eclipse.dltk.rse.feature.group \
        -installIU org.eclipse.dltk.rse.sdk.feature.group \
        -installIU org.eclipse.dltk.ruby.feature.group \
        -installIU org.eclipse.dltk.ruby.sdk.feature.group \
        -installIU org.eclipse.dltk.sh.feature.group \
        -installIU org.eclipse.dltk.sh.sdk.feature.group \
        -installIU org.eclipse.dltk.tcl.feature.group \
        -installIU org.eclipse.dltk.tcl.sdk.feature.group \
        -installIU org.eclipse.dltk.xotcl.feature.group \
        -installIU org.eclipse.dltk.xotcl.sdk.feature.group

    # Eclipse Lua plugins
    sudo eclipse -nosplash \
        -application org.eclipse.equinox.p2.director \
        -repository http://download.eclipse.org/ldt/releases/milestones/ \
        -installIU org.eclipse.ldt.feature.group\
        -installIU org.eclipse.ldt.remote.feature.group \
        -installIU org.eclipse.ldt.remote.source.feature.group \
        -installIU org.eclipse.ldt.source.feature.group
    ```



## Using Eclipse marketplace to install plugins

1. Site: [marketplace.eclipse.org](https://marketplace.eclipse.org/)

1. Install Marketplace plugin
    1. Launch Eclipse as "root"
    1. Help > Install New Software... >  Add...
        1. Location: [http://download.eclipse.org/mpc/juno](http://download.eclipse.org/mpc/juno)
        1. [x] Marketplace Client
1. Install marketplace plugins
    1. Help > Eclipse Marketplace... > Search
        1. AnyEdit Tools
        1. Eclipse Sync
        1. EGit - Git Team Provider
        1. Enide Studio (2015)
        1. GitHub Flavored markdown viewer plugin
        1. GoClipse
        1. HTML Editor (WTP)
        1. JSDT jQuery
        1. JSHint Eclipse
        1. JSON Editor Plugin
        1. Lua Development tools
        1. Maven Integration for Eclipse
        1. Natural
        1. Optimizer for Eclipse
        1. PyDev - Python IDE for Eclipse
            1. Live Coding in Python
        1. TM Terminal
        1. Trace Compass
        1. YEdit

## Manual steps

1. Set python interpreter
    1. Eclipse > Window > Preferences
        1. PyDev > Interpreters > Python Interpreter
            1. Quick Auto-Config > Apply > OK

## Plugins

1. Eclipse EGit plugin
1. Lua Development Tools

## Tips

### General

1. Starting Eclipse
    1. Optional: `sudo -i`
    1. `eclipse &`

### Eclipse editors

1. AnyEdit
    1. Install
        1. [AnyEdit tools plugin for Eclipse](http://andrei.gmxhome.de/anyedit/)
        1. `sudo eclipse -nosplash -application org.eclipse.equinox.p2.director -repository http://andrei.gmxhome.de/eclipse/ -installIU AnyEditTools.feature.group`
    1. Eclipse > Window > Preferences > General > Editors > AnyEdit Tools
        1. Auto-convert
            1. [x] Remove trailing whitespace
            1. [x] Convert tabs <-> spaces
            1. (*) Tabs to spaces
1. Show line numbers
    1. Eclipse > Window > Preferences > General > Editors > Text Editors
        1. [x] Show line numbers
1. Spaces, not tabs
    1. Eclipse > Window > Preferences > General > Editors > Text Editors
        1. [x] Insert spaces for tabs

#### Python

1. Set python interpreter
    1. Eclipse > Window > Preferences
        1. PyDev > Interpreters > Python Interpreter
            1. Quick Auto-Config > Apply > OK
1. PyLint
    1. Eclipse > Window > Preferences > PyDev
        1. PyLint
            1. [x] Use PyLint?
            1. Apply > OK
        1. Editor > Code Style > Code Formatter
            1. [x] Use autopep8.py for code formatting
1. PEP-8
    1. Eclipse > Window > Preferences > PyDev > Editor > Code Analysis > pep8.py
        1. (*) Warning
        1. [x] Use system interpreter
1. __updated__
    1. Eclipse > Window > Preferences > PyDev > Editor > Save Actions
        1. [x] Update date field?
1. Organize imports
    1. Eclipse > Window > Preferences > PyDev > Editor > Save Actions
        1. [x] Sort imports on save?
    1. Eclipse > Window > Preferences > PyDev > Editor > Code Style > Imports
        1. [x] Delete unused imports?
        1. [x] Sort 'from' imports before 'import' imports?
        1. [x] Sort individual names on grouped imports?
1. Debugging
    1. Eclipse > Right-click tool bar > Customize Perspective... > Command Groups Availability
        1. [x] PyDev Debug
    1. Eclipse > Pydev > Start Debug Server
    1. Eclipse > Pydev > Attach to Process
        1. Choose the manage.py runserver process
    1. Old [help video](https://vimeo.com/5027645)
1. Creating new python projects
    1. Eclipse > File > Project...
        1. "py" > PyDev Project > Next
        1. PyDev Project
            1. Project name:  XXXX
            1. (*) Create 'src' folder an add it to the PYTHONPATH

#### Import projects

##### Import project from Subversion

1. Add subversion repositories
    1. Eclipse > Window > Show View > Other... > SVN Repositories
    1. SVN Repositories > New Repository Location
    1. New Repository Location:
        1. URL: svn://subversion.nicehack.com/svn/...
1. Load project
    1. Eclipse > Window > Show View > Other... > SVN Repositories
    1. SVN Repositories > svn://subversion.nicehack.com/svn/.../ > xxx/trunk/xxx > Check Out

##### Import project from Git

1. Eclipse > File > Import...
1. Import
    1. Git > Projects from Git > Next
1. Import Projects from Git / Select Repository Source
    1. Existing local repository > Next
1. Import Projects from Git / Select a Git Repository
    1. If you see the path, choose it.  If not, choose "Add..."
    1. Next
1. Import Projects from Git / Select a wizard to use for importing projects
    1. (*) Import existing projects
    1. Choose topmost directory
        1. Next
1. Import Projects from Git / Import projects
    1. Check [x] project(s) to be imported
    1. Finish

##### Import project from File System

1. Eclipse > File > New > Project... > General > Project
1. Uncheck [ ] Use default location
1. Browse... for directory containing .project file
