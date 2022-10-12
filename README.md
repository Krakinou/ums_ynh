<!--
N.B.: This README was automatically generated by https://github.com/YunoHost/apps/tree/master/tools/README-generator
It shall NOT be edited by hand.
-->

# Universal Media Server for YunoHost

[![Integration level](https://dash.yunohost.org/integration/ums.svg)](https://dash.yunohost.org/appci/app/ums) ![Working status](https://ci-apps.yunohost.org/ci/badges/ums.status.svg) ![Maintenance status](https://ci-apps.yunohost.org/ci/badges/ums.maintain.svg)  
[![Install Universal Media Server with YunoHost](https://install-app.yunohost.org/install-with-yunohost.svg)](https://install-app.yunohost.org/?app=ums)

*[Lire ce readme en français.](./README_fr.md)*

> *This package allows you to install Universal Media Server quickly and simply on a YunoHost server.
If you don't have YunoHost, please consult [the guide](https://yunohost.org/#/install) to learn how to install it.*

## Overview

A DLNA, UPnP and HTTP(S) Media Server

**Shipped version:** 11.5.0
## Screenshots

![Screenshot of Universal Media Server](./doc/screenshots/screenshot.gif)

## Disclaimers / important information

### Configuration

Once installed, UMS will create config file in `/home/yunohost.app/ums/.config/UMS/`

All settings are pretty well documented directly in the files.
The default setting will use the shared multimedia directory by default (located into `/home/yunohost.multimedia/share`), you may change this setting in `/home/yunohost.app/ums/.config/UMS/UMS.conf` with the setting "folders"

### Limitations

 - No multi-instance
 - work only on its own subdomain (ums.mydomain.tld, not on mydomain.tld/ums)
 - No user management
 - Not tested that much

### Other infos

If you can't find the server on a renderer, you may try the following trouble shooting :
- Wait a little bit : the first start up will intialized the database and if you have a lot of media, this may take a while
- Wait a little more : the server will broadcast an ALIVE message every 30 sec, so it may take this long for a renderer to find it
- check if the service ums is running in the yunohost admin
- check on which network interface the server is annoucing : You may find the network and address used in `/home/yunohost.app/ums/.config/UMS/debug.log` or `/var/log/ums/ums.log`. Search for a line like `Using address /192.168.0.54 found on network interface: name:enp0s3 (enp0s3)`
The subnet to be used should be the same as your renderer (ie : if your TV is on 192.168.0.X and ums on 192.168.1.X, this will not work)

On small device (Raspberry for example), transco may be requiring too much power : try some alternate transcoder.

## Documentation and resources

* Official app website: <www.universalmediaserver.com>
* Official admin documentation: <https://github.com/UniversalMediaServer/UniversalMediaServer/wiki>
* Upstream app code repository: <https://github.com/UniversalMediaServer>
* YunoHost documentation for this app: <https://yunohost.org/app_ums>
* Report a bug: <https://github.com/YunoHost-Apps/ums_ynh/issues>

## Developer info

Please send your pull request to the [testing branch](https://github.com/YunoHost-Apps/ums_ynh/tree/testing).

To try the testing branch, please proceed like that.

``` bash
sudo yunohost app install https://github.com/YunoHost-Apps/ums_ynh/tree/testing --debug
or
sudo yunohost app upgrade ums -u https://github.com/YunoHost-Apps/ums_ynh/tree/testing --debug
```

**More info regarding app packaging:** <https://yunohost.org/packaging_apps>
