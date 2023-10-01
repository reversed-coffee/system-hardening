# User Auditing

- Manage users
    - Computer management -> Users and Groups
    - Remove unauthorized administrators
    - Disable unauthorized users
    - Change insecure passwords
        - Avoid changing current user password; can interfere with auto-login
        - Force users to change password on next login
    - Disable built-in Guest account

- User policies (Local Security Policy)
    - Follow company guidelines
    - Audit policy
        - Enable login/logout auditing
        - Enable auditing of failed login/logout attempts
    - Password policy
        - Enforce password history
        - CIS recommends 24 passwords to be remembered
        - Max password age
            - Logical discretion
            - 60 days is OK in some cases
        - Minimum password age
            - Logical discretion
            - 10 days is OK in some cases
        - Minimum password length
            - 14 characters is recommended by CIS
        - Password must meet complexity requirements
            - Always enable this
        - Store passwords using reversible encryption
            - Severe risk; always disable this

- Review user files
    - Based on company guidelines, users may not allowed to store certain forms of media on their computers
    - Delete files that are not authorized