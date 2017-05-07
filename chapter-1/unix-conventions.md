# Bash / Unix Conventions

```
~/
  bin/         # executable files by the average user
  sbin/        # executable files for the sysadmin
  lib/         # library of stuff
  libexec/     # non-chmod +x files meant to be called by other bin files
  src/         #source code files
```

# File system stuff from OMC

```
/
  mnt/       # where we mount filesystems
    log/     # logs - not backed up
    data/    # data storage - backed up
  var/
    log/     # symlinked to /mnt/log
    data/    # symlinked to /mnt/data
  dev/       # block devices
  etc/       # configuration files
  lib/       # common C libraries
```

https://en.wikipedia.org/wiki/Unix\_filesystem

https://en.wikipedia.org/wiki/Filesystem\_Hierarchy\_Standard

https://wiki.debian.org/FilesystemHierarchyStandard

