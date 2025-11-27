# Avahi-daemon IPK for WAGO Controllers

Install Avahi (mDNS/DNS‑SD) on WAGO controllers to enable zero‑configuration discovery on local networks.

## Why Zeroconf (mDNS/DNS‑SD)

- Automatic discovery: Clients find your controller/services without manual IP/DNS setup.
- Human‑friendly access: Reach it via `hostname.local`.
- Fast commissioning: Great for labs, demos, and changing topologies.
- Cross‑platform: Works with Linux, macOS, Windows (Bonjour), iOS, Android.
- Less infra: Local discovery without dedicated DNS tweaks.

## Install

### Via Web-Based Management (WBM)
For some reasons installation doesn't work properly on WP400 using the WBM. Use SSH installation.
- Connect and browse to Software upload to install on the WAGO Controller
- Select the ipk (depending on your architecture, arm64 for PFC300 and WP400, armhf for others) and click on Install

### Via SSH command line interface
- Upload the ipk (depending on your architecture, arm64 for PFC300 and WP400, armhf for others) on the device using SCP or FTP.
- Alternatively if your controller has internet access, download the package directly.

```
//arm64 version
  wget https://github.com/quenorha/avahi/raw/refs/heads/main/avahi_repo_v1.0_arm64.ipk
```

```
// arm32 (armhf) version
  wget https://github.com/quenorha/avahi/raw/refs/heads/main/avahi_repo_v1.0_armhf.ipk
```
- Install it using the following command
  ```
  opkg install -V3 avahi_repo_v1.0*.ipk
  ```

Afterward you should be able to access your controller using <hostname>.local. For instance for the controller PFC300-68415F : PFC300-68415F.local
You can also change the hostname to change the .local address.

## Troubleshooting
- Check if properly installed :
```
opkg list_installed | grep avahi
```
- Check if service is started
```
/etc/init.d/avahi-daemon status
```
- Check the logs
```
cat /var/log/messages | grep avahi
```




