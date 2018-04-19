# Test-TppObjectExists

## SYNOPSIS
Test if an object exists

## SYNTAX

### DN (Default)
```
Test-TppObjectExists -DN <String[]> [-TppSession <TppSession>] [<CommonParameters>]
```

### Guid
```
Test-TppObjectExists -Guid <String[]> [-TppSession <TppSession>] [<CommonParameters>]
```

## DESCRIPTION
Provided with either a DN path or GUID, find out if an object exists.

## EXAMPLES

### EXAMPLE 1
```
$multDNs | Test-TppObjectExist
```

Object                    Exists
--------                  -----
\VED\Policy\My folder1    True
\VED\Policy\My folder2    False

Test for existence by DN

## PARAMETERS

### -DN
DN path to object. 
Provide either this or Guid. 
This is the default if both are provided.

```yaml
Type: String[]
Parameter Sets: DN
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid
Guid which represents a unqiue object  Provide either this or DN.

```yaml
Type: String[]
Parameter Sets: Guid
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### DN or Guid.  The default is DN, but both are of type string.

## OUTPUTS

### PSCustomObject will be returned with properties 'Object', a System.String, and 'Exists', a System.Boolean.

## NOTES

## RELATED LINKS