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
    - `/etc/ssh/sshd_config` set PermitRootLogin to `no` if set to yes, make sure that it's also uncommented

- Log files `/var/log` has a bunch of stuff
    - `cat /var/log/boot.log` shows boot log
    - `journalctl -xe` shows system logs from boot to command run
    - `dmesg` shows kernel logs
