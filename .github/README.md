# FreeBSD Community Ports Tree

> [!NOTE]
> At the moment we are looking for some dedicated Community members who
can oversee this project and also merge PRs. If you are interested
please send a mail to git-admin@ or portmgr@.

This is the FreeBSD Community Ports Collection. In often times there are
cases when a specific ports cannot make it to the official tree or there
are security issues and for various reasons it is not the right choice
to be in the official tree. But the end users need the ports for
backward compatibility of may not be ready yet for upgrade or migration.
Hence this tree allows us to keep older ports in a community repository
and give the users some additional time to migrate or use.

## Frequently Asked Questions (FAQ)

### Why was my port deleted from the official ports tree and moved here?
**Answer:** The port may have been moved for the following reasons:
- The port has security issues
- The port build and works fine but there have been no upstream activity
  and hence might have undisclosed vulnerabilities
- The port is BROKEN for more than 3 months. This port can again be
  moved to the official tree once there is enough proof that it builds
  on all supported versions
- The port cannot be not packaged or has RESTRICTED licensing or needs
  additional files which have to be downloaded manually
- The port has reached End-of-Life(EOL) by upstream and this specific
  version is no longer supported by the upstream
- The port does not build on any of [FreeBSD Official Tier-1
  Architectures](https://www.freebsd.org/platforms/)
- The port requires an older version of a language or compiler which is
  no longer in the official ports tree but has been moved to the
  community tree

### Why there is no official pkg for my super port?
**Answer:** This official builder do not build this port tree at all.
As mentioned earlier pkgs which cannot be officially distributed or
poses security risks to a wider community or might jeopardise the
community value of The FreeBSD Project are not distributed from the
official channel.

### Can we create customized pkg repositories and distribute pkgs?
**Answer:** Any community member is allowed to create and distribute
pkgs on their own without any specific permissions from The FreeBSD
Project itself however this has to be done with care and reading the
specific License Requirements of each ports separately.

### Why is the `MOVED` file missing?
**Answer:** The MOVED```` file is needed for the official ports tree
to map deleted ports or ports which have moved into a different
location. This is also needed for `poudriere` to detect the changes and
pickup the new ports to build.

### Why are there so many .keepme files?
**Answer:** To have the same alike directory layouts of the official
tree the .keepme files are created as they are mostly empty directories
now. If one single port has been added to a specific category please
remove the ,keepme file in that directory.

### Are we allowed to add new categories and/or directories?
**Answer:** No. No additional categories are allowed. And please do not
create additional directories. Also please do not create any virtual
categories either.

### Why is the `UPDATING` file missing?
**Answer:** The UPDATING file is there for adding important UPDATING
information like while changing a DEFAULT_VERSIONS of a port. This does
not apply to the community tree as although most of the `USES` macros
are available but they are not usable at great extent. Let us say that
someone is adding php74 in the tree it is not possible to utilize the
`USES=php` macros. And it is also counter productive to add an entry in
the `UPDATING` file to mention about that.

### Why is there no Tools directory?
**Answer:** The Tools directory is specific to ports developers and
mostly used by the developers and in the cluster for pkg creation. This
does not apply for the community tree. Hence there is no Tools
directory.

### Why is there no Templates directory?
**Answer:** The Templates directory is specific to ports developers and
mostly used by the developers and in the cluster for pkg creation. This
does not apply for the community tree. Hence there is no Templates
directory. If there is a need to additional LICENSE templates which are
not yet in the Templates directory please submit a [bug
report](https://bugs.freebsd.org).

### Why is there no Keywords directory?
**Answer:** The Keywords directory is mainly for displaying information
which are are more or less the same in both the repository. If there is
a need to add more Keywords please submit a [bug
report](https://bugs.freebsd.org).

### Why is there no CHANGES file?
**Answer:** CHANGES file is intended for the ports develoeprs only and
there can be only one source of truth only about the major changes
hence there is no CHANGES file. Always follow the CHANGES file if there
is any concerns about the major changes happening in the official tree.

### What is the purpose of the bsd.overlay.mk file in Mk?
**Answer:** The purpose of the file is if there is a need to override a
knob from Mk/bsd.ports.mk from the official tree.

### Why is there an empty Mk/Uses directory?
**Answer:** In case there is a need to override USES macros from the
official tree it can be done here. But remember that anything added
should also be from the official Uses file plus the changes.

### Why is UIDs or GIDs file missing? How do I add UIDs/GIDs for my port?
**Answer:** For some files we need to have one source of truths only hence
these files are missing. If there is a need for specific ``UIDs or GIDs
please submit a [bug report](https://bugs.freebsd.org).
