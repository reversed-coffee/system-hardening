- View users with `cat /etc/passwd | grep /bin/bash`
    - Remove unauthorized users with `deluser --remove-home <username>`
    - Remove the home manually too `rm -rf /home/<username>`
    - Anyone who isn't root with user ID `0` needs a new user ID, `<username>:x:0` number should be changed to something else
 
- Secure `/etc/sudoers`
    - Make sure that that groups look OK
    - Expected groups are `root`, `sudo`, and `admin` can have root access
    - User exceptions should not be secure unless the company allows it
 
- Password aging `/etc/login.defs` 
    - Look for PASS_MAX_DAYS, PASS_MIN_DAYS and set it to a reasonable number like max 90 and min 30
    - `sudo chage -l mj` to view password policy info
    - Set minimum/maximum over CLI -> `sudo chage -m 30 mj && sudo chage -M 90 mj`

- User groups `/etc/group`
    - Look for `sudo` and `admin` or `adm`
    - Look for accounts that aren't authorized and delete them
    - Add user to group `sudo useradd -aG <group> <username>` or `sudo gpasswd -a <username> <group>`
 
- Add users `useradd <username>` or `adduser <username>` for Ubuntu
    - Set password using `passwd <username>`
    - Make folder `mkdir /home/<username>` and set permissions `chown <username>:<username> /home/<username>`

- Auditing filesystem
    - Look in home directories `find /home -iname "*.ext" -print
    - Pay attention for text files `*.txt`, and media files `*.mp3`, `*.mp4`, etc.
    - Remove files with `rm`
    - Dotfiles (files prepended with a `.`) are generally suspicious so inspect them

- PAM Password management `/etc/pam.d/common-password`
    - Look for `password` and set `remember` to remember a reasonable amount of passwords like 14
    - Look for more options that may increase security

- Password Quality `/etc/security/pwquality.conf`
    - Minimum length set to 14
    - Look at other stuff

- Shadow passwords `/etc/shadow`
    - Short hashes, no password, unhashed or plaintext password
    - Reset password with `passwd` and it should fix
