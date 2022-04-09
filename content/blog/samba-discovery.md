---
title: "Samba discovery windows and linux"
date: 2021-09-07T23:29:16+02:00
draft: true
tags: []
categories: []
banner: "img/banners/banner-4.jpg"
authors: ["Joseph Weigl"]
---

If you want to make your samba shares visible in Windows, Linux and MacOS maybe the following will help you.

## For Windows

You need to run https://github.com/christgau/wsdd on the server

## For Linux and Mac

You need to run avahi daemon on the server

for debian:

```shell
apt-get install avahi-daemon avahi-utils
```

but be aware that the avahi-daemon will also announce your other services. maybe you want to clean up the config in `/etc/avahi/services/` to remove SSH and website

Further you need to make sure that the avahi-daemon is running on the client

Ubuntu
```shell
sudo service avahi status
sudo service avahi start
```

Manjaro/Arch
```shell
sudo systemctl status avahi-daemon.service
sudo systemctl start avahi-daemon.service
```

