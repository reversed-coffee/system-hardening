## Removing Software
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
  
## Active Services
- `service --status-all` disable services that aren't critical
