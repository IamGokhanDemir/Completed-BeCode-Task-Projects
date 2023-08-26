
The password for Century2 is the build version of the instance of PowerShell installed on this system.

**NOTE:**
- The format is as follows:     `**.*.*****.****`
- Include all periods
- Be sure to look for the build version and NOT the PowerShell version

**IMPORTANT:**
Once you feel you have completed the Century1 challenge, start a new connection to the server and log in with the username of Century2. The password for Century2 will be the answer from Century1. If successful, close the Century1 connection and begin solving the Century2 challenge. This concept is repeated over and over until you reach the end of the game.


## Solution

To find the build version you have the use the following command:

```
$PSVersionTable
```

#### Result output command:

```
PS C:\users\century1\desktop> $PSVersionTable

Name                           Value
----                           -----
PSVersion                      5.1.14393.5127
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
BuildVersion                   10.0.14393.5127
CLRVersion                     4.0.30319.42000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

### Conclusion:

After running the command we can see the BuildVersion `10.0.14393.5127` that functions as password for Century2:
```username: century2@century.underthewire.tech
   password: 10.0.14393.5127
   user login command: ssh century2@century.underthewire.tech
```


### Here's an explanation of the command and its logic:

The code `$PSVersionTable` is used in PowerShell to retrieve information about the version of PowerShell that is currently running. It returns a hashtable containing various properties related to the PowerShell version.

1. `$PSVersionTable`: This is a predefined variable in PowerShell that holds information about the PowerShell version.

2. When this code is executed, PowerShell retrieves the value of `$PSVersionTable` and returns a hashtable containing the following properties:

   - `PSVersion`: Represents the version number of PowerShell.
   - `PSEdition`: Specifies the edition of PowerShell, such as Desktop or Core.
   - `PSCompatibleVersions`: Indicates the versions of PowerShell that are compatible with the current version.
   - `BuildVersion`: Represents the build number of PowerShell.
   - `CLRVersion`: Specifies the version of the Common Language Runtime (CLR) that PowerShell is using.
   - `WSManStackVersion`: Indicates the version of the WS-Management protocol stack used by PowerShell.
   - `SerializationVersion`: Represents the version of the serialization format used by PowerShell.

3. You can access individual properties of `$PSVersionTable` by using dot notation, for example: `$PSVersionTable.PSVersion` will give you the PowerShell version.

The logic behind using `$PSVersionTable` is to retrieve information about the current PowerShell environment, including the version and related details. This information can be useful for script compatibility checks or to determine if certain features are available in the current PowerShell version.


