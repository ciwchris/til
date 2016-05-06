Setup
----

How to add a dictionary for aspell
----------------------------------

By [default a dictionary is not installed](http://superuser.com/a/831449) and will need to be
installed using your OS's package installer.

```shell
pacman -S aspell-en
```

Setting the text width
----------------------

In vim the column length can be set using: `set textwidth=80`

In emacs the column length can be set, set-fill-column, using the command: `C-x f`

To automatically wrap text turn on [auto-fill-mode](http://stackoverflow.com/a/22751591/16973): `SPC
t f`


