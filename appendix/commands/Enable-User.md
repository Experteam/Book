# Enable-User 
 
Enables the specified Sitecore user. 
 
## Syntax 
 
Enable-User [-Identity] &lt;AccountIdentity&gt; 
 
Enable-User -Instance &lt;User&gt; 
 
 
## Detailed Description 
The Enable-User cmdlet gets a user and enables the account in Sitecore.

The Identity parameter specifies the Sitecore user to get. You can specify a user by its local name or fully qualified name.
You can also specify user object variable, such as $&lt;user&gt;. 
- 
© 2011-2015 Adam Najmanowicz - Cognifide Limited, Michael West. All rights reserved. Sitecore PowerShell Extensions 
 
## Parameters 
 
### -Identity&nbsp; &lt;AccountIdentity&gt; 
 
Specifies the Sitecore user by providing one of the following values.

    Local Name
        Example: michael
    Fully Qualified Name
        Example: sitecore\michael
 

| | |
| - | - |
| Aliases |  |
| Required? | true |
| Position? | 1 |
| Default Value |  |
| Accept Pipeline Input? | true (ByValue) |
| Accept Wildcard Characters? | false | 
 
### -Instance&nbsp; &lt;User&gt; 
 
Specifies the Sitecore user by providing an instance of a user.
 

| | |
| - | - |
| Aliases |  |
| Required? | true |
| Position? | named |
| Default Value |  |
| Accept Pipeline Input? | true (ByValue) |
| Accept Wildcard Characters? | false | 
 
## Inputs 
 
The input type is the type of the objects that you can pipe to the cmdlet. 
 
* System.String
Represents the identity of one or more users.

Sitecore.Security.Accounts.User
One or more user instances. 
 
## Outputs 
 
The output type is the type of the objects that the cmdlet emits. 
 
* System.String
Represents the identity of one or more users.

Sitecore.Security.Accounts.User
One or more user instances. 
 
## Notes 
 
Michael West 
 
## Examples 
 
### EXAMPLE 1 
 
 
 
```powershell   
 
PS master:\> Enable-User -Identity michael 
 
``` 
 
### EXAMPLE 2 
 
 
 
```powershell   
 
PS master:\> Get-User -Filter * | Enable-User 
 
``` 
 
## Related Topics 
 
* <a href='http://michaellwest.blogspot.com' target='_blank'>http://michaellwest.blogspot.com</a><br/>

