# landgear

(Land)lock (Gear) Up ; Tools to restrict software with landlock(7).

***This repo is currently in pre-alpha, and is not recommended for production!***

---

## Pre-Alpha

The point must be stressed, this repo is in pre-alpha (if there was a letter
before alpha, i'd use it). In particular, it will depend on another repo that is
being drafted. Development will take an long time and have at least one breaking
change!

It is not recommended for beginners, nor those looking for a plug-and-play
solution (yet). It is also not recommended to build on top of, unless it is
purely conceptual.

It is recommended **if and only if** you are a landlock user, experienced with
shell scripting, and would like to sandbox some applications.

## Description

In the present, this repo contains POSIX shell scripts that use [sandboxer(1)](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/samples/landlock/sandboxer.c)
to sandbox applications. Each script gives access to files, ports, and other
resources the application may need to function.

Due to the inflexible nature of the current approach, X is not supported by
default; however, this may be a trivial fix (WAYLAND\_DISPLAY --> DISPLAY).
Some applications may also require file-location tweaks - especially if you
are using MUSL.

In the future, there will be a system that resembles the Portage ebuild - where
programs inherit from base profiles and users can toggle certain features with
flags. Multiple landlock implementations (i.e landrun) will also be supported.

## Install

Copy desired files into the PATH and set them executable.

These kernel configurations are required:

- CONFIG\_SECURITY\_LANDLOCK=y
- CONFIG\_LSM=landlock

> Available in Linux kernel 5.13 and later.

These dependencies are required:

- POSIX sh
- [sandboxer](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/samples/landlock/sandboxer.c)
- xdg-dbus-proxy

> sandboxer(1) is a reference implementation from the Linux kernel. To ensure
compatibility, sandboxer must be compiled from the same tree as the active
kernel.
