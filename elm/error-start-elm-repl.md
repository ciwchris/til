When running elm-repl (when install from npm or
[nodejs-elm package](https://aur.archlinux.org/packages/nodejs-elm/)) the error would occur.

```
error while loading shared libraries: libtinfo.so.5: cannot open shared object file: No such file or directory
```

First, [libtinfo](https://aur.archlinux.org/packages/libtinfo/) needs to be installed, if it hasn't
already. (Noted as a dependency for
[buildng the Elm-Platform](https://github.com/elm-lang/elm-platform).) Next, the version of libtinfo
may be newer than he compiled binaries. Linking to the newer version seems to resolve this issue:

```shell
sudo ln -s /usr/lib/libtinfo.so.5 /usr/lib/libtinfo.so
```

[Compiling the binaries](https://aur.archlinux.org/packages/elm-platform) yourself may not produce
this error.
