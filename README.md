[//]: #@corifeus-header

  [![Build Status](https://travis-ci.org/patrikx3/openwrt-redis.svg?branch=master)](https://travis-ci.org/patrikx3/openwrt-redis)  [![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/patrikx3/openwrt-redis/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/patrikx3/openwrt-redis/?branch=master)  [![Code Coverage](https://scrutinizer-ci.com/g/patrikx3/openwrt-redis/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/patrikx3/openwrt-redis/?branch=master) 

# 📡 The OpenWrt Redis stable version package 



## The latest OpenWrt is highly EXPERIMENTAL !!!
                    
 
                        
[//]: #@corifeus-header:end

Given, that ```/var/lib``` is usually in the ROM, so the ```REDIS``` data is in actually in ```/opt/var/lib/redis``` and ```/var/lib/redis``` is a symlink to ```/opt/var/lib/redis```. I think it is good if you use ```ext-root``` or an ```SD-CARD``` based backend storage or something like.

There was a typo in the ```/etc/init.d/redis```, but now is fixed. 

## The feed

### Tested on Linksys WRT

http://cdn.corifeus.com/openwrt/SNAPSHOT/packages/arm_cortex-a9_vfpv3/redis/

```text
src/gz reboot_redis http://cdn.corifeus.com/openwrt/SNAPSHOT/packages/arm_cortex-a9_vfpv3/redis
```

### Tested on D-Link DIR 860L B1

http://cdn.corifeus.com/openwrt/SNAPSHOT/packages/mipsel_24kc/redis/

```text
src/gz reboot_redis http://cdn.corifeus.com/openwrt/SNAPSHOT/packages/mipsel_24kc/redis
```

### RPI-3

http://cdn.corifeus.com/openwrt/SNAPSHOT/packages/aarch64_cortex-a53/redis/

```text
src/gz reboot_redis http://cdn.corifeus.com/openwrt/SNAPSHOT/packages/aarch64_cortex-a53/redis/
```


## Built package:
  
* Like Linksys WRT ARM ```atomic instructions```
  * https://cdn.corifeus.com/openwrt/SNAPSHOT/packages/arm_cortex-a9_vfpv3/redis/  

* Like D-Link RAMIPS ```pthreads```
  * https://cdn.corifeus.com/openwrt/SNAPSHOT/packages/mipsel_24kc/redis/

* RPI-3 
  * http://cdn.corifeus.com/openwrt/SNAPSHOT/packages/aarch64_cortex-a53/redis/

## The router service

Please, where you can find it in  [OPENWRT-INSOMNIA](https://pages.corifeus.com/openwrt-insomnia), of course it includes ```init.d``` service as well.

```bash
/etc/init.d/redis stop|start
```

## Your own build

```bash
cp feeds.conf.default feeds.conf
echo 'src-git redis https://github.com/patrikx3/openwrt-redis.git' >> feeds.conf
./scripts/feeds update -a
./scripts/feeds install -a
./scripts/feeds update redis
./scripts/feeds install -a -p  redis

# create a .config
make menuconfig

# either
make package/feeds/redis/redis/{clean,prepare,compile} package/index V=s

# or
make V=s
```


# PS

This is based on:
https://github.com/chrisber/openwrt-ipkg-redis and https://github.com/pdf/openwrt-14.07-x86_64-packages/tree/master/net/redis .

It will be in all of my [OPENWRT-INSOMNIA](https://pages.corifeus.com/openwrt-insomnia).

### CPU type
Right now, I only tested on ARM (Linksys WRT1200ACS, Linksys 3200ACM) and D-Link RAMIPS since it is 4.0.9

# Built from

http://download.redis.io/releases/


[//]: #@corifeus-footer

---

[**P3X-OPENWRT-REDIS**](https://pages.corifeus.com/openwrt-redis) Build v4.0.217-103 

[![Like Corifeus @ Facebook](https://img.shields.io/badge/LIKE-Corifeus-3b5998.svg)](https://www.facebook.com/corifeus.software) [![Donate for Corifeus / P3X](https://img.shields.io/badge/Donate-Corifeus-003087.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=QZVM4V6HVZJW6)  [![Contact Corifeus / P3X](https://img.shields.io/badge/Contact-P3X-ff9900.svg)](https://www.patrikx3.com/en/front/contact) 


## P3X Sponsors

[IntelliJ - The most intelligent Java IDE](https://www.jetbrains.com)
  
[![JetBrains](https://cdn.corifeus.com/assets/svg/jetbrains-logo.svg)](https://www.jetbrains.com/) [![NoSQLBooster](https://cdn.corifeus.com/assets/png/nosqlbooster-70x70.png)](https://www.nosqlbooster.com/)

[The Smartest IDE for MongoDB](https://www.nosqlbooster.com)
  
  
 

[//]: #@corifeus-footer:end



