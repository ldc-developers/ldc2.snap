ldc2.snap
=========

This project defines a snap package for LDC, the LLVM-based compiler for
the D programming language.  It is an 'external' snap, meaning that it
downloads and builds the source from the official LDC git repo.

The LDC project aims to provide a portable compiler for the D language,
with modern optimization and code generation capabilities.  It uses the
official DMD compiler frontend to support the latest version of D2, and
uses the LLVM Core libraries for code generation.  For more information
on LDC, see: https://github.com/ldc-developers/ldc

The D programming language is a systems programming language with C-like
syntax and static typing.  It combines efficiency, control and modelling
power with safety and programmer productivity.  For more information on
the D language, see: https://dlang.org/

Snap packages are designed to provide secure, containerized applications
that are appropriately sandboxed away from the rest of the system they
are running on.  For more information on snap packages, see:
http://snapcraft.io/


Building
--------

On Ubuntu 16.04 or higher with snapcraft installed
(`sudo apt install snapcraft`):

    git clone https://github.com/ldc-developers/ldc2.snap.git
    cd ldc2.snap
    snapcraft

Since ldc2 is packaged as a `classic` snap, the `snapcraft cleanbuild`
command is not currently supported.  This is expected to be fixed with
upcoming releases of `snapcraft`, so try it if you like, just don't be
surprised if it fails with linker errors.


Installing
----------

LDC has been packaged as a `classic` snap, so installing it requires the
`--classic` flag to be used in order to grant the necessary confinement
permissions.  Self-built snaps are unsigned and therefore also require
the `--dangerous` flag in order to install them:

    sudo snap install --classic --dangerous ldc2_VERSION_amd64.snap

replacing `VERSION` as appropriate.

For more information on `classic` confinement, see:
https://insights.ubuntu.com/2017/01/09/how-to-snap-introducing-classic-confinement/
