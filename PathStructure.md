# Recommended path structure #

## Rationale ##

Because I would like not to alter the original TinyOS source tree, I use GNU `stow` command to merge this project's source tree with the original one.

## Path structure ##

```
/opt/tinyos/
           sources/
                   tinyos-2.x
                   tinyos-cortex
           root/
           scripts/
                    envsetup.subr
/opt/cortex/
somewhere/build/
          scripts-tinyos-cortex/
                                config.subr
                                toolchain.sh
          scripts-cortex/
                         config.subr
                         toolchain.sh
```

## Details ##

`/opt/tinyos`:

> This is where whole TinyOS related stuff will live in.  This directory is configurable by `prefix` variable within the `scripts-tinyos-cortex/config.subr`.

`/opt/cortex`:
> This is where whole cortex toolchain related stuff will live in.  This directory is configurable by `prefix` variable within the `scripts-cortex/config.subr`.

`somewhere/build`:
> This is the directory where all build scripts will be executed from.  In building process, a couple of source tar balls will be downloaded here and also a couple of repositories will be checked out here.  You need not keep this directory's contents after building and installation are finished.  You can install TinyOS and cortex toolchain by:

```
$ mkdir -p somewhere/build
$ cd somewhere/build
$ git clone https://code.google.com/p/tinyos-cortex.scripts-tinyos/ scripts-tinyos-cortex
$ git clone https://code.google.com/p/tinyos-cortex.scripts-cortex/ scripts-cortex
$ ./scripts-tinyos-cortex/toolchain.sh
$ ./scripts-cortex/toolchain.sh
$ ./scripts-tinyos-cortex/toolchain.sh cleanup
$ ./scripts-cortex/toolchain.sh cleanup
```

`/opt/tinyos/root`:
> This is `TOSROOT` directory.  Both the TinyOS main stream source tree and tinyos-cortex source tree will be merged under this directory by stow command.

`/opt/tinyos/sources/tinyos-2.*`:
> This is the TinyOS main stream source tree.

`/opt/tinyos/sources/tinyos-cortex*`:
> This is the tinyos-cortex source tree which will be merged with TinyOS main stream source tree.

`/opt/tinyos/scripts`:
> This directory has scripts to setup the TinyOS development environment.  You can `source` `scripts/envsetup.subr` shell script from login or session shell to set environment variables, such as `PATH` and `TOSROOT` etc.
```
# in your ~/.bashrc
source /opt/tinyos/scripts/envsetup.subr
```

`/opt/cortex/scripts`:
> This directory has scripts to setup cortex development environment.  You can `source` `scripts/envsetup.subr` shell script from login or session shell to set environment variables, such as `PATH` and `MANPATH` etc.
```
# in your ~/.bashrc
source /opt/cortex/scripts/envsetup.subr
```