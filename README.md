# avahi


```
https://github.com/quenorha/avahi/raw/refs/heads/main/avahi_0.8_armhf.ipk
https://github.com/quenorha/avahi/raw/refs/heads/main/libdaemon_0.14_armhf.ipk
opkg install -V3 libdaemon_0.14_armhf.ipk
opkg install -V3 avahi_0.8_armhf.ipk
useradd -r -s /bin/false avahi
/etc/init.d/avahi-daemon start
```
