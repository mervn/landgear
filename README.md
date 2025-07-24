# landgear

This repo supplies templates and tools to restrict software with landlock(7).

> This repo is in pre-alpha. In particular, it will depend on another repo that
is being drafted. Development will take an extended period of time and have at
least one breaking change!

## Install

Copy desired files into the PATH and set them executable.

System depends on:

- landlock

> landlock(7) requires a 5.13+ kernel, CONFIG\_SECURITY\_LANDLOCK=y, and
CONFIG\_LSM=landlock.

Runtime depends on:

- POSIX sh
- [sandboxer](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/samples/landlock/sandboxer.c)
- xdg-dbus-proxy

> sandboxer(1) is a reference implementation from the Linux kernel. To ensure
compatibility, sandboxer must be compiled from the same tree as the active
kernel.
