---
id: troubleshooting
title: Troubleshooting 
---

Troubleshooting {#_troubleshooting}
===============

Common issues include the following.

**Agents don't show up in IDE.**

Try:

-   Restarting the IDE

-   Logging in again

**Username Field is Disabled in Login.**

Try:

-   Make sure the backend server is reachable

-   Make sure the URL/port were typed correctly

-   Try deleting and retyping a character in the URL to trigger
    validation again

-   Make sure there are no hidden characters/spaces before/after the URL

![Notification warning - \"Lightrun actions in this file were submitted
against a different
version...​\"](../../img/source-version-warning-notification.png)

This notification warning pops up when one or more actions in the open
file were set against different source code. This might happen if you
set an action after making edits to the file, or if an action was set to
the same file by another person whose source code differs from yours.

This warning can be ignored, as it doesn't block the activation of the
action. However, actions set on mismatching source code can cause
unexpected behavior, so it is recommended to solve the issue.

To solve the issue, make sure that the application you are debugging is
the same as the code in your editor (or the editor of whoever set the
action). If the problem persists, you can disable the warning by
clicking \"Don't Show this Again\" in the notification panel (Notice
that disabling this feature will also affect the actions the way other
people view the actions you set).

Certificates issues {#_certificates_issues}
-------------------

### Self-signed certificate is blocked {#_self_signed_certificate_is_blocked}

The troubleshooting may vary depends on either browser (also browser
version) or OS, and the following cover most of the popular browsers and
operating systems

1.  [Getting Chrome to accept self-signed localhost certificate (per
    Chrome
    version)](https://stackoverflow.com/questions/7580508/getting-chrome-to-accept-self-signed-localhost-certificate)

2.  [Ubuntu: Adding a self-signed certificate to the "trusted
    list"](https://unix.stackexchange.com/questions/90450/adding-a-self-signed-certificate-to-the-trusted-list)

3.  [Creating and Trusting Self-Signed Certs on MacOS and
    Chrome/Safari](https://www.andrewconnell.com/blog/updated-creating-and-trusting-self-signed-certs-on-macos-and-chrome/)

4.  [How to trust a self-signed SSL certificate in IE11 and
    Edge](https://medium.com/@ali.dev/how-to-trust-any-self-signed-ssl-certificate-in-ie11-and-edge-fa7b416cac68)

5.  [How do you get Chrome to accept a self-signed certificate on
    Win10](https://www.pico.net/kb/how-do-you-get-chrome-to-accept-a-self-signed-certificate)
