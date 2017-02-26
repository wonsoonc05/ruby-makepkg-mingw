## ruby-makepkg-mingw

### mingw/msys2 package builders for Ruby build dependencies

### IMPORTANT NOTES:

All the included scripts use the --skippgpcheck flag, which bypasses the pgp checking.  All files are checked for SHA256.

It is assumed that you are familiar with using the msys2/mingw shell and path commands.

### Purpose

This repo is for initial development and testing of msys2/mingw2 packages for Ruby builds. In particular, to work with [larskanis/rubyinstaller2](https://github.com/larskanis/rubyinstaller2).

Once the packages/code is well tested, both will hopefully be accepted into the msys2/mingw ecosystem, and there won't be any further active developement, except if new package versions are needed.

I've tested these packages with builds of Ruby trunk, they need to be tested with previous versions.  If they don't work, additional package versions may be needed.

### Description

Three Ruby dependencies are provided, gdbm, libyaml, and openssl.

gdbm is version 1.10, libyaml is 0.1.7, openssl is 1.1.0e.

### Creating the packages

Three scripts are provided for creating the packages:
```
ruby_make_all - creates 32 bit and 64 bit packages
ruby_make_32  - creates 32 bit packages
ruby_make_64  - creates 64 bit packages
```

From the mingw64 shell, run them with a full path.  On my system, the command is 
```
/d/GitHub/ruby-makepkg-mingw/ruby_make_all`
```

Building all six versions may take quite a while (30+ minutes).  If you're building with Windows, you might want to disable any firewall security, as the OpenSSL tests will hit it.

Test result files are in the test_results folder.  Your results should match.  Please check before adding the packages.

### Installing the packages

Likewise, three scripts are provided:

Three scripts are provided for creating the packages:
```
ruby_pacman_all
ruby_pacman_32
ruby_pacman_64
```

As above, run them with a full path.  You may need to confirm each packages installation.

If you decide to re-run the creation scripts, I might suggest deleting the src and build folders first.

I threw the scripts and this readme together rather quickly.  I've only tested the 'all' scripts.