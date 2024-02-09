---
title: 'Sudo for Windows'
date: '2024-02-09T10:59:09Z'
draft: false
tags:
- Windows
- Sudo
- PowerShell
---

Wow. Sudo for Windows is here! 

See the official announcement in a Microsoft Devblogs [here](https://devblogs.microsoft.com/commandline/introducing-sudo-for-windows/).

Sudo for Windows is a new way for users to run elevated commands directly from an unelevated console session. It is an ergonomic and familiar solution for users who want to elevate a command without having to first open a new elevated console.

I gave it a try, and it seems to be doing what it says on the tin.

Once enabled in Windows System Settings (_For Developers_ Section) like so:

![Windows System Settings](/img/for-developers-settings2.png)

When elevating a process from the command-line with sudo, a UAC dialog will appear asking the user to confirm the elevation:

![UAC Dialog](/img/uac-dialog.png)

If you are curious how this thing works, here is a diagram from the official announcement:

![Sudo for Windows Diagram](/img/sudo-diagram.png)

And here's how you invoke it:

```powershell
sudo choco upgrade python
```

Overall, I am sure the sudo will save some clicks to the users and make the Windows command-line experience more enjoyable.
