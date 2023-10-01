# Browser Security

## Security Levels

| Symbol | Security Level | Risk Mitigation |
---------|----------------|------------------
| 😐     | Moderate       | High risks      |
| 😳     | High           | Moderate risks  |
| 😠     | Aggressive     | Low risks       |
| 😈     | Paranoid       | Privacy         |

## Best Practices

- Update the browser
    - Latest version
    - Automatically install updates

- Look for signs of compromise
    - Do any malicious tabs automatically open?
    - Is the search engine overwritten?
    - What extensions are installed?

## Configuration

- Secure HTTP
    - 😐 Ensure that the browser can verify certificates
        - ! Invalid certificates on websites pose a phishing risk
    - 😐 Enable HTTPS-only mode
        - ! Websites without HTTPS support pose a phishing risk
        - ! Websites without HTTPS are subject to MITM attacks

- Dangerous content
    - 😐 Block malicious software
        - 😐 Warn users when an extension is prompted for installation
            - ! Malicious extensions can execute code on the browser
        - 😐 Warn users when PUPs/malware are downloaded
            - ! Poses a system breach risk
    - 😐 Clear notification subscriptions
        - ! Malicious notifications can be used to social engineer or show explicit content
        - 😠 Block notifications
            - ! Notifications can pose a low risk, but if they're not needed, it's best to disable them
    - 😳 Block pop-up windows
        - ! Pop-up windows are known to show malicious webpages

- Login Keychain
    - ! Inherently has potential privacy risks, especially on shared devices
    - 😠 Do not ask to save login or payment information
        - 😠 Disable saving login information
        - 😠 Remove all saved login information
    - 😐 Disable autofill
        - 😠 Remove all saved autofill data
    - 😐 Show breach alerts for passwords

- History
    - 😈 Clear history
    - 😈 Never remember history
        - ! History is not necessary in many cases

- Tracker Control
    - 😠 DNT (Do Not Track) header
        - ! Tracks privacy-respecting trackers
    - Cookie protection
        - ! Some settings can break some sites
        - 😐 Block in-site cryptominers
        - 😠 Block cross-site cookies
        - 😠 Block miscellaneous trackers
        - 😈 Block fingerprinting

- Secure DNS (DNS over HTTPS)
    - ! Make sure that this isn't restricted by round guidelines; Using secure DNS may block DNS-based content blockers
    - 😠 Enable Secure DNS
    - 😈 Enable strict mode
