# Get-SearchIndex 
 
Returns sitecore Search indices. 
 
## Syntax 
 
Get-SearchIndex [[-Name] &lt;String&gt;] 
 
 
## Detailed Description 
Returns sitecore Search indices. 
- 
© 2011-2015 Adam Najmanowicz - Cognifide Limited, Michael West. All rights reserved. Sitecore PowerShell Extensions 
 
## Parameters 
 
### -Name&nbsp; &lt;String&gt; 
 
Name of the index to return.
 

| | |
| - | - |
| Aliases |  |
| Required? | false |
| Position? | 2 |
| Default Value |  |
| Accept Pipeline Input? | false |
| Accept Wildcard Characters? | false | 
 
## Notes 
 
Help Author: Adam Najmanowicz, Michael West 
 
## Examples 
 
### EXAMPLE 
 
 
 
```powershell   
 
PS master:\>Get-SearchIndex | ft -auto
 
Name   Analyzer                                      Directory
----   --------                                      ---------
system Lucene.Net.Analysis.Standard.StandardAnalyzer Lucene.Net.Store.SimpleFSDirectory@C:\Projects\ZenGarden\Data\indexes\__system lockFactory=Sitecore.Search.SitecoreLockFactory
WeBlog Lucene.Net.Analysis.Standard.StandardAnalyzer Lucene.Net.Store.SimpleFSDirectory@C:\Projects\ZenGarden\Data\indexes\WeBlog lockFactory=Sitecore.Search.SitecoreLockFactory 
 
``` 
 
## Related Topics 
 
* <a href='https://github.com/SitecorePowerShell/Console/' target='_blank'>https://github.com/SitecorePowerShell/Console/</a><br/>

