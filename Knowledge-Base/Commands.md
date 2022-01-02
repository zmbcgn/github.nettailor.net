Auf dieser Seite habe ich ein paar Shell Commands erfasst, die ich immer mal wieder brauche. Quasi als Quick-Reference-Guide

# Linux
`dpkg --get-selections > ~/Package.list`

Ausgabe von allen installierten Paketen in die Datei 'Package.list'

# Windows

# Windows (WSL2)

Ein Netzlaufwerk in der WSL verfügbar machen:

```
sudo mkdir /mnt/s
sudo mount -t drvfs '\\netzwerkserver\freigabe\ordner' /mnt/s
```
[Quelle](https://superuser.com/questions/1128634/how-to-access-mounted-network-drive-on-windows-linux-subsystem/1261563#1261563)