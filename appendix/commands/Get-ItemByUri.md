# Get-ItemByUri 
 
This commandlet has been obsoleted - use "Get-Item -Uri" instead. 
 
## Syntax 
 
Get-ItemByUri [-ItemUri &lt;String&gt;] 
 
 
## Detailed Description 
This commandlet has been obsoleted - use "Get-Item -Uri" instead. 
- 
© 2011-2015 Adam Najmanowicz - Cognifide Limited, Michael West. All rights reserved. Sitecore PowerShell Extensions 
 
## Parameters 
 
### -ItemUri&nbsp; &lt;String&gt; 
 

 

| | |
| - | - |
| Aliases |  |
| Required? | false |
| Position? | named |
| Default Value |  |
| Accept Pipeline Input? | false |
| Accept Wildcard Characters? | false | 
 
## Notes 
 
Help Author: Adam Najmanowicz, Michael West 
 
## Examples 
 
### EXAMPLE 
 
 
 
```powershell   
 
PS master:\> Get-Item -Path master: -Uri "sitecore://master/{658017A8-F2D9-45C2-B89E-1B55A9FCFEE2}?lang=en&ver=1" 
 
``` 
 
## Related Topics 
 
* <a href='https://github.com/SitecorePowerShell/Console/' target='_blank'>https://github.com/SitecorePowerShell/Console/</a><br/>

