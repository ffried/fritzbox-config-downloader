fritzbox-config-downloader
==========================

Downloads a configuration backup of an AVM Fritz!Box to the a file.
Originally developed for automatic backups with rsnapshot.
It supports downloading the config through the internet using remote access.
The configuration is ecrypted with no password, a password of your choice or "admin" as default. Without a password you cannot
load the config into another Fritz!Box.

Usage: `./fritzbox-config-downloader [arguments]`

| Argument              | Description              | Default   |
|:----------------------|:-------------------------|:----------|
| -h Hostname[:Port] | Hostname or IP of the Fritz!Box to backup. Port is optional. | Default is "fritz.box". |
| -u Username | Username for newer versions of Fritz!OS and for remote access. | Default is no username. |
| -p Password | Password for the Fritzbox. | Default is no password. |
| -e ExportPassword | Password for the backup file. | If present but no password set, the default is "admin". |
| -o OutputFile | Output file to store the downloaded config. | Defaults to `./FritzBox.export` |
| -r | Set to enable remote access to the Fritz!Box over the internet using HTTPS. | |
| -s SecondPassword | Older Fritz!Box models secure remote access with HTTP-Auth. If the Fritz!Box has a password for local access to the webinterface this password is needed, too. In this case, pass the remote access password as using the `-p` argument and the local webinterface password using this `-s` argument. Fritz!OS 5.50 fixes this Bug, it doesn't need this parameter anymore. So in most cases you won't need this argument. | Default is no password. |



freetz-config-downloader
==========================

The same as the fritzbox-config-downloader, but for the full Fritzbox+Freetz configuration
for modded boxes. After downloading the config, it's saved as Fritzbox.freetz.
For use with rsnapshot the Backup is then extracted into the folder var_flash (Fritzbox)
and flash (freetz).

Usage: `./freetz-config-downloader [hostname [Password [Username]]]`

| Argument | Description | Default |
|:---------|:------------|:--------|
| Hostname | Hostname or IP of the Fritzbox to backup. Portnumber is currently fixed to 81. | Default is "fritz.box". |
| Password | Password of the Freetz web interface. | Default is freetz. |
| Username | Username of the Freetz web interface. | Default is admin. |
