# Get-UpdatePackageDiff 
 
Performs a diff operation between the Source and taget path akin to Sitecore Courier. The diff is the difference that takes the content of Source folder and transforms it to Target.
IMPORTANT! This functionality requires changes to web.config file on your sitecore server to work. Please consult the first Example. 
 
## Syntax 
 
Get-UpdatePackageDiff [-SourcePath] &lt;String&gt; [[-TargetPath] &lt;String&gt;] 
 
 
## Detailed Description 
 
Performs a diff operation between the Source and taget path akin to Sitecore Courier. The diff is the difference that takes the content of Source folder and transforms it to Target.
IMPORTANT! This functionality requires changes to web.config file on your sitecore server to work. Please consult the first Example. 
 
© 2010-2017 Adam Najmanowicz, Michael West. All rights reserved. Sitecore PowerShell Extensions 
 
## Parameters 
 
### -SourcePath&nbsp; &lt;String&gt; 
 
Path containing the current serialization items that needs to be transformed into Target. 
 
<table>
    <thead></thead>
    <tbody>
        <tr>
            <td>Aliases</td>
            <td></td>
        </tr>
        <tr>
            <td>Required?</td>
            <td>true</td>
        </tr>
        <tr>
            <td>Position?</td>
            <td>1</td>
        </tr>
        <tr>
            <td>Default Value</td>
            <td></td>
        </tr>
        <tr>
            <td>Accept Pipeline Input?</td>
            <td>false</td>
        </tr>
        <tr>
            <td>Accept Wildcard Characters?</td>
            <td>false</td>
        </tr>
    </tbody>
</table> 
 
### -TargetPath&nbsp; &lt;String&gt; 
 
Path containing the desired serialization state that the Source needs to be transformed to. 
 
<table>
    <thead></thead>
    <tbody>
        <tr>
            <td>Aliases</td>
            <td></td>
        </tr>
        <tr>
            <td>Required?</td>
            <td>false</td>
        </tr>
        <tr>
            <td>Position?</td>
            <td>1</td>
        </tr>
        <tr>
            <td>Default Value</td>
            <td></td>
        </tr>
        <tr>
            <td>Accept Pipeline Input?</td>
            <td>false</td>
        </tr>
        <tr>
            <td>Accept Wildcard Characters?</td>
            <td>false</td>
        </tr>
    </tbody>
</table> 
 
## Outputs 
 
The output type is the type of the objects that the cmdlet emits. 
 
* Sitecore.Update.Interfaces.ICommand 
 
## Notes 
 
Help Author: Adam Najmanowicz, Michael West 
 
## Examples 
 
### EXAMPLE 1 
 
Required addition to web.config file for the functionality to work: 
 
```powershell   
 
<configuration>
  <configSections>
    <section name="sitecorediff" type="Sitecore.Update.Configuration.ConfigReader, Sitecore.Update"/>
  </configSections>
  <sitecorediff>
    <commandfilters>
      <filter id="changedFieldsFilter" mode="on" type="Sitecore.Update.Commands.Filters.ChangedFieldsFilter, Sitecore.Update">
        <fields hint="list">
          <field>__Created</field>
          <field>{5DD74568-4D4B-44C1-B513-0AF5F4CDA34F}</field>
          <field>__Revision</field>
          <field>__Updated</field>
          <field>__Updated by</field>
        </fields>
      </filter>
    </commandfilters>
    <dataproviders>
      <dataprovider id="filesystemmain" type="Sitecore.Update.Data.Providers.FileSystemProvider, Sitecore.Update">
        <param>$(id)</param>
      </dataprovider>
      <dataprovider id="snapshotprovider" type="Sitecore.Update.Data.Providers.SnapShotProvider, Sitecore.Update">
        <param>$(id)</param>
      </dataprovider>
    </dataproviders>

    <source type="Sitecore.Update.Data.DataManager, Sitecore.Update">
      <param>source</param>
    </source>

    <target type="Sitecore.Update.Data.DataManager, Sitecore.Update">
      <param>target</param>
    </target>
  </sitecorediff>
</configuration> 
 
``` 
 
### EXAMPLE 2 
 
Create an update package that transforms the serialized database state defined in C:\temp\SerializationSource into into set defined in C:\temp\SerializationTarget 
 
```powershell   
 
$diff = Get-UpdatePackageDiff -SourcePath C:\temp\SerializationSource -TargetPath C:\temp\SerializationTarget
Export-UpdatePackage -Path C:\temp\SerializationDiff.update -CommandList $diff -Name name 
 
``` 
 
## Related Topics 
 
* [Export-UpdatePackage](/appendix/commands/Export-UpdatePackage.md)* [Install-UpdatePackage](/appendix/commands/Install-UpdatePackage.md)* <a href='http://sitecoresnippets.blogspot.com/2012/10/sitecore-courier-effortless-packaging.html' target='_blank'>http://sitecoresnippets.blogspot.com/2012/10/sitecore-courier-effortless-packaging.html</a><br/>* <a href='https://github.com/adoprog/Sitecore-Courier' target='_blank'>https://github.com/adoprog/Sitecore-Courier</a><br/>* <a href='https://github.com/SitecorePowerShell/Console/' target='_blank'>https://github.com/SitecorePowerShell/Console/</a><br/>
