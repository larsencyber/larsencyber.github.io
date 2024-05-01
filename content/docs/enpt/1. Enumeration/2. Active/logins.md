---
title: Login Portals
weight: 4
sidebar:
  open: true
---
It's extremely important to enumerate all possible login portals to various systems and infrastructure in an External Penetration Test.
The best chance at cracking the perimeter is by compromising a valid user account.

## Office 365
Office 365 login portals are easily discovered, however they are not great for penetration testers.

This is due to [Microsoft Entra Smart Lockout](https://learn.microsoft.com/en-us/entra/identity/authentication/howto-password-smart-lockout) which is enabled by default for all Microsoft Entra customers. It can quickly tell whether sign-ins are coming from valid users or attackers. In the case of an External Penetration Test where the project sponsor is supplied typically only a couple of source IP addresses where testing will come from, these will be quickly denylisted by Smart Lockout. Therefore, it's important to identify any other legacy login endpoints to breach the perimeter. 
```
Work in progress.
```

## Outlook Web Access
```
Work in progress.
```

## RDWeb
Work in progress.