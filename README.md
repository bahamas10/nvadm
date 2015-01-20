nvadm(1) - Node.js Version Admin
================================

Manage installed versions of [Node.js](http://nodejs.org) using precompiled
packages

Example
-------

List available versions of node to install

    $ ./nvadm ls
    current version

    node: v0.10.35
    npm: 1.4.28

    available versions: http://nodejs.org/dist

    - node 0.8.x - 
    v0.8.0    v0.8.1    v0.8.2    v0.8.3    v0.8.4    v0.8.5    
    v0.8.6    v0.8.7    v0.8.8    v0.8.9    v0.8.10   v0.8.11   
    v0.8.12   v0.8.13   v0.8.14   v0.8.15   v0.8.16   v0.8.17   
    v0.8.18   v0.8.19   v0.8.20   v0.8.21   v0.8.22   v0.8.23   
    v0.8.24   v0.8.25   v0.8.26   v0.8.27   v0.8.28   
    - node 0.9.x - 
    v0.9.0    v0.9.1    v0.9.2    v0.9.3    v0.9.4    v0.9.5    
    v0.9.6    v0.9.7    v0.9.8    v0.9.9    v0.9.10   v0.9.11   
    v0.9.12   
    - node 0.10.x - 
    v0.10.0   v0.10.1   v0.10.2   v0.10.3   v0.10.4   v0.10.5   
    v0.10.6   v0.10.7   v0.10.8   v0.10.9   v0.10.10  v0.10.11  
    v0.10.12  v0.10.13  v0.10.14  v0.10.15  v0.10.16  v0.10.16-isaacs-manual
    v0.10.17  v0.10.18  v0.10.19  v0.10.20  v0.10.21  v0.10.22  
    v0.10.23  v0.10.24  v0.10.25  v0.10.26  v0.10.27  v0.10.28  
    v0.10.29  v0.10.30  v0.10.31  v0.10.32  v0.10.33  v0.10.34  
    v0.10.35  
    - node 0.11.x - 
    v0.11.0   v0.11.1   v0.11.2   v0.11.3   v0.11.4   v0.11.5   
    v0.11.6   v0.11.7   v0.11.8   v0.11.9   v0.11.10  v0.11.11  
    v0.11.12  v0.11.13  v0.11.14  


Install node `v0.10.35`

    $ sudo ./nvadm in v0.10.35
    using cache dir ~/.nvadm
    downloading http://nodejs.org/dist/v0.10.35/node-v0.10.35-sunos-x86.tar.gz... done
    installing ~/.nvadm/node-v0.10.35-sunos-x86.tar.gz to /opt/local
    running: tar --no-same-owner --strip-components=1 -xz -f /home/dave/.nvadm/node-v0.10.35-sunos-x86.tar.gz -C /opt/local
    done!

    installed!

    /opt/local/bin/node: v0.10.35
    /opt/local/bin/npm: 1.4.28

You can also install different architectured (32bit, 64bit, etc.) to custom directories

    $ ./nvadm in -p /var/tmp/node-testing v0.11.10 x64
    using cache dir ~/.nvadm
    downloading http://nodejs.org/dist/v0.11.10/node-v0.11.10-sunos-x64.tar.gz... done
    installing /home/dave/.nvadm/node-v0.11.10-sunos-x64.tar.gz to /var/tmp/node-testing
    running: tar --no-same-owner --strip-components=1 -xz -f /home/dave/.nvadm/node-v0.11.10-sunos-x64.tar.gz -C /var/tmp/node-testing
    done!

    installed!

    /var/tmp/node-testing/bin/node: v0.11.10
    /var/tmp/node-testing/bin/npm: 1.3.22

Usage
-----

    $ ./nvadm help
    Usage: nvadm <command> [options]

    Manage Node.js versions

    Commands
      list        list all possible node versions to install
      install     install a given version of node
      help        this message

    Install Options
      -p <dir>    prefix dir, defaults to operating system prefix
      -v          verbose mode
      -z          dry-run, don't actually install anything

    Examples
      list all available node versions
        nvadm list

      install a specific version of node
        nvadm install v0.8.8
        - defaults to x86 for the current operating system

      install node for a specific platform
        nvadm install v0.8.8 x64 sunos

License
-------

MIT License
