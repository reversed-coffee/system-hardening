## Software
- Use `aptitude` to inspect packages
    - Look for hacking tools, servers, etc.
- `apt install` to install, `apt remove` to remove, `apt purge` to completely remove, `apt autoremove` to clean up
- Make sure to run `update` and `upgrade`
- Ubuntu Software Center
    - Open with `software-properties-gtk`
    - Turn off proprietary software and restricted software
    - Install security and recommended updates
    - Check for updates as often as possible
    - Download and install updates automatically
- Quick system update: `sudo apt-get update && sudo apt-get upgrade -y`
- Using DPKG to search for packages `sudo dpkg --list | grep <name>`
    - Hacking tools may have keywords `crack`, `sniff`, `analyze`, `hack`, etc.
    - Make sure the package is safe to remove!
  
## Active Services
- `service --status-all` disable services that aren't critical

- Securing SSH
    - If not critical, disable and stop the service `sudo systemctl disable sshd && sudo systemctl stop sshd`
    - `/etc/ssh/sshd_config`
         - Set PermitRootLogin to `no` if set to yes, make sure that it's also uncommented
         - Set PermitEmptyPasswords to `no` as well
    - Check for overrides in `/etc/ssh/sshd.config.d`
    - Check file permissions in `/etc/ssh/` look for keys and config permissions especially - only `root` should have access to them

- Log files `/var/log` has a bunch of stuff
    - `cat /var/log/boot.log` shows boot log
    - `journalctl -xe` shows system logs from boot to command run
    - `dmesg` shows kernel logs
         - Restrict `dmesg` it can have important information
              - `sudo sysctl -w kernel.dmesg_restrict=1`
              - `/etc/sysctl.conf` enable there too

- TCP SYN Cookie Protection
    - `sudo sysctl -w -n net.ipv4.tcp_syncookies=1`
    - `/etc/sysctl.conf` uncomment `net.ipv4.tcp_syncookies=1`
 
- NGINX `/etc/nginx`
    - Inspect headers, stuff like always enabling sameorigin is not OK
    - Set `server_tokens off` in `http`
    - Use TLS 1.0, 1.1, 1.2, 1.3
    - Prefer server ciphers too
    - Look at anything else on there
