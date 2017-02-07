# Openwrt dist
[![Build Status](https://travis-ci.org/simonsmh/openwrt-dist.svg?branch=master)](https://travis-ci.org/simonsmh/openwrt-dist)  
Build with Travis Ci daily.  
This dist is for OpenWrt 15.05 devices only.
[You may want original project there.](http://openwrt-dist.sourceforge.net)

## Usage
You can use the following command to get architecture.  
`opkg print-architecture | awk '{print $2}'`

Then, check your architecture in all branches and add the following line to `/etc/opkg.conf`. 
```
src/gz simonsmh_base https://github.com/simonsmh/openwrt-dist/raw/{architecture}/base
src/gz simonsmh_packages https://github.com/simonsmh/openwrt-dist/raw/{architecture}/packages
```

Then install what you want.
```
opkg update
opkg install ChinaDNS
opkg install luci-app-chinadns
opkg install dns-forwarder
opkg install luci-app-dns-forwarder
opkg install shadowsocks-libev
opkg install luci-app-shadowsocks
opkg install pdnsd
opkg install luci-app-pdnsd
```
For more detail please check the `base` directory. You can also search and install them in LuCI or SCP/FTP upload these downloaded files to your router, then login to your router and use opkg to install these .ipk file.
## Build it yourself
[Check here](https://github.com/simonsmh/openwrt-dist/blob/master/.travis.yml)

## License
GPLv3

## Credit
Copyright © 201 simonsmh
