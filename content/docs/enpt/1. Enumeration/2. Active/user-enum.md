---
title: Username Enumeration
weight: 5
sidebar:
  open: true
---
There is a Microsoft 365 API (GetCredentialType https://login.microsoftonline.com/common/GetCredentialType) which can be used to determine which user accounts supplied exist in a Microsoft Azure tenancy.

## AAD Internals
AADInternals is a powerful PowerShell module that can interact directly with Azure AD and Microsoft 365. 

https://aadinternals.com/aadinternals/ 

https://github.com/Gerenios/AADInternals 

1. Installation from PowerShell:
```powershell
# Install the module
Install-Module AADInternals

# Import the module
Import-Module AADInternals
```

2. Populate valid users in a `users.txt` file:
```txt
user@company.com  
user2@company.com 
admin@company.com 
admin2@company.com  
external.user_gmail.com#EXT#@company.onmicrosoft.com
external.user_outlook.com#EXT#@company.onmicrosoft.com
```

3. Validate list of usernames:
```powershell
Get-Content .\users.txt | Invoke-AADIntUserEnumerationAsOutsider -Method Normal
```

Output:
```powershell
UserName                                               Exists
--------                                               ------
user@company.com                                       True
user2@company.com                                      False
admin@company.com                                      True
admin2@company.com                                     False
external.user_gmail.com#EXT#@company.onmicrosoft.com   True
external.user_outlook.com#EXT#@company.onmicrosoft.com False
```

Further reading: https://aadinternals.com/post/just-looking/