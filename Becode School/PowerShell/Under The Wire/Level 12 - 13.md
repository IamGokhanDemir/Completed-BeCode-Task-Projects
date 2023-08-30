
The password for Century13 is the description of the computer designated as a Domain Controller within this domain **PLUS** the name of the file on the desktop.  
  
**NOTE:**  
– The password will be lowercase no matter how it appears on the screen.  
– If the description “today_is” and the file on the desktop is named “_cool”, the password would be “today_is_cool”.

## Solution

To find the first part of the password we first have find the name of the domain controller, we can do that by using the `Get-ADDomainController | Select-Object name` and then we find that the name in this case is `UTW`. After finding the name we have to find the description of the domain controller here we use the name we found in the first part `UTW` in the next command `Get-ADComputer UTW -Properties Description`, and we see under the description we find the first part of the password `i_authenticate`. The second part of the password is easy we just use the `ls` command in the desktop folder and then we get under NAME the second part of the password `_things`

```
PS C:\users\century12\desktop> Get-ADDomainController |
Select-Object name

name
----
UTW


PS C:\users\century12\desktop> Get-ADComputer UTW -Prope
rties Description


Description       : i_authenticate
DistinguishedName : CN=UTW,OU=Domain
                    Controllers,DC=underthewire,DC=tech
DNSHostName       : utw.underthewire.tech
Enabled           : True
Name              : UTW
ObjectClass       : computer
ObjectGUID        : 5ca56844-bb73-4234-ac85-eed2d0d01a2
                    e
SamAccountName    : UTW$
SID               : S-1-5-21-758131494-606461608-355627
                    0690-1000
UserPrincipalName :



PS C:\users\century12\desktop> ls


    Directory: C:\users\century12\desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/30/2018   3:34 AM             30 _thing
                                                 s


PS C:\users\century12\desktop> ls


    Directory: C:\users\century12\desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/30/2018   3:34 AM             30 _thing
                                                 s
```

## Conclusion 

We first had to use the `Get-ADDomainController | Select-Object name` command to find the domain name to able to use in the `Get-ADComputer UTW -Properties Description` to able to find the first part of the password.

#### Result

```
password: i_authenticate_things
user login command: ssh century13@century.underthewire.tech
```

### Here's an explanation of the command and its logic:

The command `Get-ADDomainController | Select-Object name` explained:

```powershell
Get-ADDomainController | Select-Object name
```

This command performs the following actions:

1. `Get-ADDomainController`: Retrieves a list of Active Directory domain controllers in the current domain.

2. `|`: Passes the output of the previous command as input to the next command.

3. `Select-Object name`: Selects only the `name` property from the domain controller objects. This command will display the names of the domain controllers.

The command's logic involves querying Active Directory for domain controllers and then selecting and displaying their names. By executing this command, you will obtain a list of domain controller names for the current domain.

The command `Get-ADComputer UTW -Properties Description` explained:

```powershell
Get-ADComputer UTW -Properties Description
```

This command performs the following actions:

1. `Get-ADComputer`: Retrieves Active Directory computer objects based on specified filters or search criteria.

2. `UTW`: Specifies the name or distinguished name of the computer object you want to retrieve.

3. `-Properties Description`: Specifies the properties of the computer object to include in the output. In this case, we are interested in the `Description` property.

The command's logic involves querying Active Directory for the computer object with the name "UTW" and retrieving its `Description` property. By executing this command, you will obtain the description of the specified computer object.