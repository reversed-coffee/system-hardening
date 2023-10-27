# Software Auditing

- Update software
    - Check program version
        - May be under Help -> About
        - Check version by viewing binary's properties
    - Check for updates & automatically update
        - May be under the Help menu
        - Not all software has these features
    - Check version and install new versions online
        - Use official sites to find version
        - Ensure the site has HTTPS so we have a secure download
        - Hash check if a hash is provided

- Update Windows
    - In security competitions, time is of the essence
    - It's best to start downloading and installing updates ASAP

- Review applications
    - Uninstall applications that are not critical or used for business
        - Control Panel -> Programs and Features
        - Tools like CCleaner may be used as well (Make sure its usage is allowed!)
    - Find portable applications
        - These generally are not allowed, so uninstall them if allowed
    - Universally critical applications
        - .NET Framework Runtimes
        - Visual C++ Runtimes
        - Java Runtime
            - Is Java up to date?

- Removing unneeded features
    - Control Panel -> Programs -> Turn Windows features on or off (appwiz.cpl)
    - Check if any critical software is requried
        - Remove features are not critical and may pose a risk, such as LPD Print Service
    - In some cases a reboot may be necessary for features to be completely removed

- Services
    - Windows Update - Enable
    - Remote Desktop Services - Allows RDP
    - Remote Registry - Disable, allows remote modification of Windows registry, which can allow for privilege escalation
    - SNMP Trap - Disable, MiTM risk
    - SSDP Discovery - Disable
 
- View live network connections with `netstat`
    - Can be used to find odd connections, especially connections to C2 servers

- Application hardening
    - Web browsers
        - See [Browser Security](../universal/Browser-Security.md)
