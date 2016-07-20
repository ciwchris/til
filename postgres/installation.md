## Arch

```
sudo pacman -S postgresql
sudo passwd postgres
su postgres
initdb --locale $LANG -E UTF8 -D '/var/lib/postgres/data'
exit
systemctl start postgresql.service
```
