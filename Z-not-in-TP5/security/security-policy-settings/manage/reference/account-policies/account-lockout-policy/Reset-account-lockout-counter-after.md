---
title: Reset account lockout counter after
ms.custom: na
ms.prod: windows-server-2012
ms.reviewer: na
ms.suite: na
ms.technology: 
  - techgroup-security
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 71fe80d4-8de5-435e-905c-d65b72e5c916
---
# Reset account lockout counter after
This security policy reference topic for the IT professional describes the best practices, location, values, and security considerations for this policy setting.  
  
## Reference  
The **Reset account lockout counter after** policy setting determines the number of minutes that must elapse from the time a user fails to log on before the failed logon attempt counter is reset to 0. If **Account lockout threshold** is set to a number greater than zero, this reset time must be less than or equal to the value of **Account lockout duration**.  
  
A disadvantage to setting this too high is that users lock themselves out for an inconveniently long period if they exceed the account lockout threshold through logon errors. Users may make excessive Help Desk calls.  
  
This policy setting is supported on versions of Windows that are designated in the **Applies To** list at the beginning of this topic.  
  
### Possible values  
  
-   A user\-defined number of minutes from 1 through 99,999  
  
-   Not defined  
  
### Best practices  
  
-   You need to determine the threat level for your organization and balance that against the cost of your Help Desk support for password resets. Each organization will have specific requirements.  
  
### Location  
*GPO\_name***\\Computer Configuration\\Windows Settings\\Security Settings\\Account Policies\\Account Lockout Policy**  
  
### Default values  
The following table lists the actual and effective default policy values for the most recent supported versions of Windows. Default values are also listed on the policy’s property page.  
  
|Server type or Group Policy Object \(GPO\)|Default value|  
|----------------------------------------------|-----------------|  
|Default domain policy|Not defined|  
|Default domain controller policy|Not defined|  
|Stand\-alone server default settings|Not applicable|  
|Domain controller effective default settings|Not defined|  
|Member server effective default settings|Not defined|  
|Client computer effective default settings|Not applicable|  
  
### Operating system version differences  
There are no differences in the way this policy setting works between [supported versions of Windows](#BKMK_top).  
  
## Security considerations  
This section describes how an attacker might exploit a feature or its configuration, how to implement the countermeasure, and the possible negative consequences of countermeasure implementation.  
  
### Vulnerability  
Users can accidentally lock themselves out of their accounts if they mistype their password multiple times.  
  
### Countermeasure  
Configure the **Reset account lockout counter after** policy setting to 30.  
  
### Potential impact  
If you do not configure this policy setting or if the value is configured to an interval that is too long, an attacker could attempt to log on to each user's account numerous times and lock out their accounts, a denial\-of\-service \(DoS\) attack might succeed, or administrators might have to manually unlock all locked\-out accounts. If you configure this policy setting to a reasonable value, users can perform new attempts to log on after a failed logon within a reasonable time, without making brute force attacks feasible at high speeds. Be sure that you notify users of the values that are used for this policy setting so that they wait for the lockout timer to expire before they call the Help Desk.  
  
## See Also  
[Account Lockout Policy](Account-Lockout-Policy.md)  
  
