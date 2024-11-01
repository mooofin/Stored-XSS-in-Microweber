# Exploit Title: Stored XSS in Microweber
# Date: 06/18/2024
# Vendor Homepage: (https://microweber.me/)
# Version: 2.0.15
# Tested on: (http://active.demo.microweber.me/)

## Vulnerability Description
A Stored Cross-Site Scripting (XSS) vulnerability has been identified in Microweber version 2.0.15. This vulnerability allows an attacker to inject malicious scripts that get stored on the server and executed in the context of another user's session.

## Steps to Reproduce
1. Log in to the application.
2. Navigate to `Users > Edit Profile`.
3. In the `First Name` field, input the following payload:

    "><img src=x onerror=confirm(document.cookie)>

4. Save the changes.
5. Upon visiting any page where the modified user profile is displayed, an alert box will appear, indicating the execution of the injected script.