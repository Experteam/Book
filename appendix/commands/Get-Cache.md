# Get-Cache 
 
Retrieves a Sitecore cache. 
 
## Syntax 
 
Get-Cache [[-Name] &lt;String&gt;] 
 
 
## Detailed Description 
Retrieves a Sitecore cache. 
- 
© 2011-2015 Adam Najmanowicz - Cognifide Limited, Michael West. All rights reserved. Sitecore PowerShell Extensions 
 
## Parameters 
 
### -Name&nbsp; &lt;String&gt; 
 
Name of the cache to retrieve. Supports wildcards.
 

| | |
| - | - |
| Aliases |  |
| Required? | false |
| Position? | 1 |
| Default Value |  |
| Accept Pipeline Input? | false |
| Accept Wildcard Characters? | false | 
 
## Notes 
 
Help Author: Adam Najmanowicz, Michael West 
 
## Examples 
 
### EXAMPLE 
 
 
 
```powershell   
 
PS master:\> Get-Cache -Name master*

Name                                     Enabled       Count       Size   Max Size Default  Scavengable
                                                                                   Priority
----                                     -------       -----       ----   -------- -------- -----------
master[blobIDs]                          True              0          0     512000   Normal       False
master[blobIDs]                          True              0          0     512000   Normal       False
master[blobIDs]                          True              0          0     512000   Normal       False
master[itempaths]                        True            292     108228   10485760   Normal       False
master[standardValues]                   True             57      38610     512000   Normal       False
master[paths]                            True            108      13608     512000   Normal       False
master[items]                            True           1010    5080300   10485760   Normal       False
master[data]                             True           3427    7420654   20971520   Normal       False 
 
``` 
 
## Related Topics 
 
* <a href='https://github.com/SitecorePowerShell/Console/' target='_blank'>https://github.com/SitecorePowerShell/Console/</a><br/>

