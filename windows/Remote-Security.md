# Remote Security

- Windows Firewall
    - Windows Defender Firewall (firewall.cpl)
    - Ensure that Windows Firewall is enabled
    - Review and update firewall entries
    - Manage firewall exceptions
        - Entries that allow UPnP can be questionable 

- Review certificates on system
    - Certificate Manager: certmgr.msc
    - Remove sketchy certificates
        - Untrusted, expired, or untrusted certificates
    - Remove untrusted root CAs
        - Company root CA is generally allowed
    - This is done because rouge certificates can pose MITM risks

- Remote Desktop Protocol (RDP) and Remote Assistance
    - Control Panel -> System -> Properties (sysdm.cpl) -> Remote
    - If not critical, ensure that it's disabled
    - If critical, secure it by restricting it to users that need it
    - If remote assistance is not allowed by company policy, disable it
    - Group policies
        - Windows Compontents -> Remote Desktop Services -> Session Host -> Security
        - Set client connection encryption level - High level, enabled
        - Require use of specific security layer - SSL, enabled

- Virtual Network Computing (VNC)
    - Managed by third party software
        - If not needed, uninstall it
    - Hardening can vary
        - Update software
        - Use secure authentication
        - Add firewall entries
            - Only allow certain computers to connect
        - Use encryption
        - Avoid default ports
        - Strong access control
            - Restrict connections to certain users
        - Enable logs
        - Disable uneccesary features

- Secure Shell (SSH)
    - Disable if not required
        - Generally OpenSSH service
    - Use private key authentication instead of passwords
    - Firewall rules
        - Only allow certain computers to connect
    - Limit who you can log in as
    - Avoid default ports

- File sharing services
    - Review content that is shared remotely
        - Do you NEED to share the entire C drive?
    - Manage access control accordingly
        - Restrict who can connect to the file sharing server
    - Server Manager -> Storage Services -> Shares
        - Modify permissions
     
- Securing SMB
    - If using SMB 1.0, remove it and install newer edition
 
- Server Manager -> Local Server -> IE Enhanced Security - Enable
