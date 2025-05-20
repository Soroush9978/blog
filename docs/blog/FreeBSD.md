# First encounter with freeBSD
Recently I have Installed FreeBSD on some relatively old hardware Thinkpad X201 :)), here I gather the things that I will learn and had learn through the process
# FreeBSD: A Comprehensive Guide

FreeBSD is a powerful, secure, and highly customizable Unix-like operating system known for its performance, advanced networking stack, and ZFS filesystem. This guide covers installation, administration, and optimization based on discussions with DeepSeek Chat.

---

## 1. Installing FreeBSD
FreeBSD offers a straightforward installation process via its text-based installer.

### Key Steps:
- Download the latest **ISO** from [FreeBSD.org](https://www.freebsd.org/).
- Boot into the installer and follow the prompts.
- **Partitioning**:
  - For ZFS, select **Auto (ZFS)** for a modern setup.
  - For UFS, choose **Manual** partitioning for traditional setups.
- Configure networking (DHCP or static IP).
- Set the root password and create a user account.

### Post-Installation Setup
```sh
pkg update && pkg upgrade -y  # Update packages
pkg install sudo bash git     # Install essential tools
```
## 2. Basic FreeBSD Commands
FreeBSD uses a mix of traditional Unix commands and its own utilities.

Command	Description
```
freebsd-version	Check FreeBSD version
pkg install <package>	Install a package
service <service> start	Start a service
ifconfig	Network configuration (legacy)
ipfw	Firewall management
zfs list	List ZFS datasets
bsdinstall	Re-run the installer
```
## 3. Managing Services
FreeBSD uses rc.d for service management.

```sh
service sshd start      # Start SSH
service nginx enable    # Enable at boot
service nginx restart   # Restart a service
For modern systems, use sysrc:
```
```sh
sysrc nginx_enable=YES  # Enable nginx at boot
```
## 4. Networking in FreeBSD
FreeBSD’s networking stack is highly optimized.

Key Config Files:
/etc/rc.conf → Network & service settings

/etc/resolv.conf → DNS settings

/etc/hosts → Static host entries

Using PF (Packet Filter) Firewall
FreeBSD’s default firewall is PF. Example rules:

```sh
# /etc/pf.conf
ext_if = "em0"
block all
pass in on $ext_if proto tcp to port {22, 80, 443}
Enable it with:
sysrc pf_enable=YES
service pf start
```
## 5. ZFS: The Ultimate Filesystem
FreeBSD’s integration with ZFS is one of its strongest features.

Basic ZFS Commands:
```sh
zpool create mypool mirror /dev/ada0 /dev/ada1  # Create mirrored pool
zfs create mypool/data                         # Create dataset
zfs set compression=lz4 mypool/data            # Enable compression
zfs snapshot mypool/data@backup                # Take snapshot
```
## 7. Performance Tuning
FreeBSD is highly tunable. Key optimizations:

Kernel Tweaks (/boot/loader.conf):
```sh
kern.ipc.shmseg=1024
kern.maxfiles=200000
Network Tuning (/etc/sysctl.conf):
net.inet.tcp.sendbuf_max=16777216
net.inet.tcp.recvbuf_max=16777216
```
## 8. Security Best Practices
Disable root SSH login:

```sh
echo "PermitRootLogin no" >> /etc/ssh/sshd_config
service sshd restart
Enable automatic updates:
pkg install cronie
echo "0 3 * * * root /usr/sbin/pkg update -q && /usr/sbin/pkg upgrade -y" >> /etc/crontab
```

