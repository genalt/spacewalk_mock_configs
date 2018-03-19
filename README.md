# Mock configs to build rpm packages of spacewalk project


See details about spacewalk project here [https://spacewalkproject.github.io/](https://spacewalkproject.github.io/)


## Description

Mock is a simple program that will build source RPMs inside a chroot. It doesn't do anything terribly fancy other than populate a chroot with the contents specified by a configuration file, then build any input **SRPM(s)** in that chroot.

```
mock [options] --rebuild SRPM [SRPM...]
```

The content of a chroot is specified by the configuration specified with the **-r** option. The default configuration file is /etc/mock/default.cfg, which is usually a symlink to one of the installed configurations.

There is a site-wide configuration file, /etc/mock/site-defaults.cfg, which can be used to specify site-wide options. The shipped version of this file has no active options, but does have a list of all of the configuration options, examples of how to set them, and their default values.

For backwards compatibility, old-style commands, ("rebuild", "init", "clean", etc.) without leading '--' are still accepted, but are deprecated. See COMMANDS section, below, for detailed listing of all commands.

To use mock, a user should become a member of the **mock** group by adding their username to the mock line in /etc/group. This can be done with the following command:

```
sudo /usr/sbin/usermod -a -G mock $USER
```

Note that mock is not intended to be run directly as root.
