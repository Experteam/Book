# New-ExplicitFileSource 
 
Creates new File source that can be added to a Sitecore package. 
 
## Syntax 
 
New-ExplicitFileSource [-Name] &lt;String&gt; [-File &lt;FileSystemInfo&gt;] 
 
 
## Detailed Description 
Creates new File source that can be added to a Sitecore package. Folder provided as Root will be added as well as all of its content provided it matches the filters. 
- 
© 2011-2015 Adam Najmanowicz - Cognifide Limited, Michael West. All rights reserved. Sitecore PowerShell Extensions 
 
## Parameters 
 
### -Name&nbsp; &lt;String&gt; 
 
Name of the file source.
 

| | |
| - | - |
| Aliases |  |
| Required? | true |
| Position? | 1 |
| Default Value |  |
| Accept Pipeline Input? | false |
| Accept Wildcard Characters? | false | 
 
### -File&nbsp; &lt;FileSystemInfo&gt; 
 
Path to the file to be included. this can be automatically discovered if a stream of files is piped to the commandlet.
 

| | |
| - | - |
| Aliases |  |
| Required? | false |
| Position? | named |
| Default Value |  |
| Accept Pipeline Input? | true (ByValue) |
| Accept Wildcard Characters? | false | 
 
## Notes 
 
Help Author: Adam Najmanowicz, Michael West 
 
## Examples 
 
### EXAMPLE 
 
Following example creates a new package, adds content of the Console folder (except the source files) under the site folder
saves it in the Sitecore Package folder + gives you an option to download the saved package. 
 
```powershell   
 
# Create package
       $package = new-package "Sitecore PowerShell Extensions";

# Set package metadata
       $package.Sources.Clear();

       $package.Metadata.Author = "Adam Najmanowicz - Cognifide, Michael West";
       $package.Metadata.Publisher = "Cognifide Limited";
       $package.Metadata.Version = "2.7";
       $package.Metadata.Readme = 'This text will be visible to people installing your package'
       
# Add content of the Console folder (except the source files) located in the site folder to the package
       $source = Get-ChildItem -exclude *.cs -Path "$AppPath\Console" -Recurse -File | New-ExplicitFileSource -Name "Console Assets"
       $package.Sources.Add($source);

# Save package
       Export-Package -Project $package -Path "$($package.Name)-$($package.Metadata.Version).zip" -Zip

# Offer the user to download the package
       Download-File "$SitecorePackageFolder\$($package.Name)-$($package.Metadata.Version).zip" 
 
``` 
 
## Related Topics 
 
* Export-Package 
 
* Get-Package 
 
* Import-Package 
 
* Install-UpdatePackage 
 
* New-ExplicitItemSource 
 
* New-FileSource 
 
* New-ItemSource 
 
* New-Package 
 
* <a href='https://github.com/SitecorePowerShell/Console/' target='_blank'>https://github.com/SitecorePowerShell/Console/</a><br/> 
 
* <a href='http://blog.najmanowicz.com/2011/12/19/continuous-deployment-in-sitecore-with-powershell/' target='_blank'>http://blog.najmanowicz.com/2011/12/19/continuous-deployment-in-sitecore-with-powershell/</a><br/> 
 
* <a href='https://gist.github.com/AdamNaj/f4251cb2645a1bfcddae' target='_blank'>https://gist.github.com/AdamNaj/f4251cb2645a1bfcddae</a><br/> 
 
* <a href='https://www.youtube.com/watch?v=60BGRDNONo0&list=PLph7ZchYd_nCypVZSNkudGwPFRqf1na0b&index=7' target='_blank'>https://www.youtube.com/watch?v=60BGRDNONo0&list=PLph7ZchYd_nCypVZSNkudGwPFRqf1na0b&index=7</a><br/>

