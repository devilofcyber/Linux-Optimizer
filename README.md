# Linux Optimizer

## This Bash script automates the optimization of your Linux server.
#### Notes:
 1. This script is designed for execution on Linux server environments, including VPS, VDS, Dedicated, and Bare Metal systems. It is not recommended for use on Linux desktop environments.
 2. Modifying the kernel (options 1 and 2) may result in removing or resetting some GPU drivers.
 3. Some VMs do not support kernel changes (options 1 and 2). Installing XanMod could cause the VM to break. Please be cautious and test beforehand.

### It performs the following tasks:
       
0. Fix `hosts` file and DNS:
    - Check and add 127.0.1.1 and server hostname to `/etc/hosts`.
    
    *Original `hosts` file is backed up at `/etc/hosts.bak`.*
    - Add `1.1.1.1`, `1.0.0.1` nameservers to `/etc/resolv.conf`.
    
    *Original `dns` file is backed up at `/etc/resolv.conf.bak`.*


1. Update, Upgrade, and Clean the server:
    - _Update_
    - _Upgrade_
    - _Full-Upgrade_
    - _AutoRemove_
    - _AutoClean_
    - _Clean_


2. Disable Terminal Ads.


3. Install XanMod Kernel:
    - Enable BBRv3.
    - CloudFlare TCP Optimizations.
    - More Details: https://xanmod.org

4. Install Useful Packages:

    _`apt-transport-https`_ _`apt-utils`_ _`autoconf`_ _`automake`_ _`bash-completion`_ _`bc`_ _`binutils`_ _`binutils-common`_ _`binutils-x86-64-linux-gnu`_ _`build-essential`_ _`busybox`_ _`ca-certificates`_ _`cron`_ _`curl`_ _`dialog`_ _`epel-release`_ _`gnupg2`_ _`git`_ _`haveged`_ _`htop`_ _`jq`_ _`keyring`_ _`libssl-dev`_ _`libsqlite3-dev`_ _`libtool`_ _`locales`_ _`lsb-release`_ _`make`_ _`nano`_ _`net-tools`_ _`packagekit`_ _`preload`_ _`python3`_ _`python3-pip`_ _`qrencode`_ _`socat`_ _`screen`_ _`software-properties-common`_ _`ufw`_ _`unzip`_ _`vim`_ _`wget`_ _`zip`_


5. Enable Packages at Server Boot.

    
6. Set the server TimeZone to the VPS IP address location.

 
7. Create & Enable `SWAP` File:
    - Swap Path: `"/swapfile"`
    - Swap Size: `2Gb`


8. Enable `IPv6` Support.


9. Optimize the [SYSCTL](https://github.com/devilofcyber/Linux-Optimizer/blob/main/files/sysctl.conf) Configs:
    - Optimize File System Settings.
    - Optimize Network Core Settings.
    - Optimize `SWAP`.
    - Optimize `TCP` and `UDP` Settings.
    - Optimize `UNIX` Domain Sockets Settings.
    - Optimize `Virtual memory (VM)` Settings.
    - Optimize Network Configuration Settings.
    - Optimize the Kernel.
    - Activate `BBR` _(`BBRv3` with XanMod)_.

    *Original file is backed up at `/etc/sysctl.conf.bak`.*

    
10. Optimize [SSH](https://github.com/devilofcyber/Linux-Optimizer/blob/main/files/sshd_config):
    - Disable DNS lookups for connecting clients.
    - Remove less efficient encryption ciphers.
    - Enable and Configure TCP keep-alive messages.
    - Allow TCP forwarding.
    - Enable gateway ports, Tunneling and compression.
    - Enable X11 Forwarding.

    *Original file is backed up at `/etc/ssh/sshd_config.bak`.*
   

11. Optimize the [System Limits](https://github.com/devilofcyber/Linux-Optimizer/blob/main/files/profile):
    - Soft and Hard *ulimit* `-c -d -f -i -l -n -q -s -u -v -x` optimizations.
    
    
12. Optimize `UFW` and open SSH Ports:
    - Open Ports `SSH`.
    - With `IPv6`.

    
Reboot at the end is Recommended.


## Prerequisites

### Ensure that the `sudo` and `wget` packages are installed on your system:

- Ubuntu & Debian:
```
sudo apt update -q && sudo apt install -y sudo wget
```

## Run
#### **Tested on:** Ubuntu 20+, Debian 11+

#### Root Access is Required. If the user is not root, first run:
```
sudo -i
```
#### Then:
```
wget "https://raw.githubusercontent.com/devilofcyber/Linux-Optimizer/main/linux-optimizer.sh" -O linux-optimizer.sh && chmod +x linux-optimizer.sh && bash linux-optimizer.sh 
```


## Menu Image
### Debian & Ubuntu:
![debian-based-menu](https://raw.githubusercontent.com/devilofcyber/Linux-Optimizer/refs/heads/main/assets/1.png)


## Disclaimer
This script is provided as-is, without any warranty or guarantee. Use it at your own risk.


## A Special Thanks to
- [hawshemi](https://github.com/hawshemi/)


## License
This script is licensed under the MIT License.

