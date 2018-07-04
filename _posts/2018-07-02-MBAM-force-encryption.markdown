---
layout: post
title:  "How to force BitLocker encryption after MBAM agent install"
date:   2018-07-02 09:22:47 +0200
categories: Microsoft BitLocker MBAM
---

So you made GPOs, distributed MBAM clients and waited for several hours (even days?) but encryption do not start ...

Those are few commands that can help diagnosing what happens and why are you waiting ...

### Start the client within minute(s) ...
Add the **DWORD** key **NoStartupDelay** to the 
**HKLM\Software\Microsoft\MBAM**
with value of **1** 
and restart MBAM client service for this change to take effect. You should get prompt for PIN or see that encryption started.

### Check for status from command prompt
> manage-bde -status

and explanation is on this [link](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/manage-bde)

## Check the reason why machine is not compliant from PowerShell
> gwmi -class mbam_volume -Namespace root\microsoft\mbam

This will give you numbers as reason(s) for (non)compliance and explanation of those numbers are on this [link](https://docs.microsoft.com/en-us/Microsoft-desktop-optimization-pack/mbam-v25/determining-why-a-device-receives-a-noncompliance-message "Determining why a Device Receives a Noncompliance Message") 
