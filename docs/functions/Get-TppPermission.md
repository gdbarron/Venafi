# Get-TppPermission

## SYNOPSIS
Get permissions for TPP objects

## SYNTAX

### ByObject (Default)
```
Get-TppPermission -InputObject <TppObject> [-IdentityId <String[]>] [-Explicit] [-Attribute <String[]>]
 [-TppSession <TppSession>] [<CommonParameters>]
```

### ByPath
```
Get-TppPermission -Path <String[]> [-IdentityId <String[]>] [-Explicit] [-Attribute <String[]>]
 [-TppSession <TppSession>] [<CommonParameters>]
```

### ByGuid
```
Get-TppPermission -Guid <Guid[]> [-IdentityId <String[]>] [-Explicit] [-Attribute <String[]>]
 [-TppSession <TppSession>] [<CommonParameters>]
```

## DESCRIPTION
Get permissions for users and groups on any object.
The effective permissions will be retrieved by default, but inherited/explicit permissions can optionally be retrieved.
You can retrieve all permissions for an object or for a specific user/group.

## EXAMPLES

### EXAMPLE 1
```
Get-TppObject -Path '\VED\Policy\My folder' | Get-TppPermission
```

Get all assigned effective permissions for users/groups on a specific policy folder

### EXAMPLE 2
```
Get-TppObject -Path '\VED\Policy\My folder' | Get-TppPermission -Explicit
```

Get explicit and implicit permissions for users/groups on a specific policy folder

### EXAMPLE 3
```
Find-TppObject -Path '\VED' -Recursive | Get-TppPermission -IdentityId 'AD+myprov:jasdf87s9dfsdfhkashfg78f7'
```

Find assigned permissions for a specific user across all objects

## PARAMETERS

### -InputObject
TppObject representing an object in TPP, eg.
from Find-TppObject or Get-TppObject

```yaml
Type: TppObject
Parameter Sets: ByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Full path to an object

```yaml
Type: String[]
Parameter Sets: ByPath
Aliases: DN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid
Guid representing a unique object

```yaml
Type: Guid[]
Parameter Sets: ByGuid
Aliases: ObjectGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityId
Specifying this optional parameter will only return objects that have permissions assigned to this id.
You can use Find-TppIdentity to search for identities.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PrefixedUniversalId, ID

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Explicit
Get explicit (direct) and implicit (inherited) permissions instead of effective.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ExplicitImplicit

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Attribute
Retrieve identity attribute values for the users and groups.
Attributes include Group Membership, Name, Internet Email Address, Given Name, Surname.
This parameter will be deprecated in a future release.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TppSession
Session object created from New-TppSession method. 
The value defaults to the script session object $TppSession.

```yaml
Type: TppSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $Script:TppSession
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### InputObject, Path, Guid, IdentityId
## OUTPUTS

### PSCustomObject with the following properties:
###     Path
###     Guid
###     Name
###     TypeName
###     IdentityId
###     IdentityPath
###     IdentityName
###     EffectivePermissions (if Explicit switch is not used)
###     ExplicitPermissions (if Explicit switch is used)
###     ImplicitPermissions (if Explicit switch is used)
###     Attribute (if Attribute parameter provided, to be deprecated)
## NOTES

## RELATED LINKS

[http://venafitppps.readthedocs.io/en/latest/functions/Get-TppPermission/](http://venafitppps.readthedocs.io/en/latest/functions/Get-TppPermission/)

[https://github.com/gdbarron/VenafiTppPS/blob/master/VenafiTppPS/Code/Public/Get-TppPermission.ps1](https://github.com/gdbarron/VenafiTppPS/blob/master/VenafiTppPS/Code/Public/Get-TppPermission.ps1)

[https://github.com/gdbarron/VenafiTppPS/blob/master/VenafiTppPS/Code/Public/Get-TppIdentityAttribute.ps1](https://github.com/gdbarron/VenafiTppPS/blob/master/VenafiTppPS/Code/Public/Get-TppIdentityAttribute.ps1)

[https://docs.venafi.com/Docs/20.4SDK/TopNav/Content/SDK/WebSDK/r-SDK-GET-Permissions-object-guid.php?tocpath=Web%20SDK%7CPermissions%20programming%20interface%7C_____3](https://docs.venafi.com/Docs/20.4SDK/TopNav/Content/SDK/WebSDK/r-SDK-GET-Permissions-object-guid.php?tocpath=Web%20SDK%7CPermissions%20programming%20interface%7C_____3)

[https://docs.venafi.com/Docs/20.4SDK/TopNav/Content/SDK/WebSDK/r-SDK-GET-Permissions-object-guid-external.php?tocpath=Web%20SDK%7CPermissions%20programming%20interface%7C_____4](https://docs.venafi.com/Docs/20.4SDK/TopNav/Content/SDK/WebSDK/r-SDK-GET-Permissions-object-guid-external.php?tocpath=Web%20SDK%7CPermissions%20programming%20interface%7C_____4)

[https://docs.venafi.com/Docs/20.4SDK/TopNav/Content/SDK/WebSDK/r-SDK-GET-Permissions-object-guid-local.php?tocpath=Web%20SDK%7CPermissions%20programming%20interface%7C_____5](https://docs.venafi.com/Docs/20.4SDK/TopNav/Content/SDK/WebSDK/r-SDK-GET-Permissions-object-guid-local.php?tocpath=Web%20SDK%7CPermissions%20programming%20interface%7C_____5)

[https://docs.venafi.com/Docs/20.4SDK/TopNav/Content/SDK/WebSDK/r-SDK-GET-Permissions-object-guid-principal.php?tocpath=Web%20SDK%7CPermissions%20programming%20interface%7C_____7](https://docs.venafi.com/Docs/20.4SDK/TopNav/Content/SDK/WebSDK/r-SDK-GET-Permissions-object-guid-principal.php?tocpath=Web%20SDK%7CPermissions%20programming%20interface%7C_____7)

