---
author: jpjofre
description: 
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
manager: carolz
ms.date: 2016-09-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkID=113427
schema: 2.0.0
title: Write-Output
---

# Write-Output
## SYNOPSIS
Sends the specified objects to the next command in the pipeline.
If the command is the last command in the pipeline, the objects are displayed in the console.
## SYNTAX

```
Write-Output [-InputObject] <PSObject[]> [<CommonParameters>]
```

## DESCRIPTION
The Write-Output cmdlet sends the specified object down the pipeline to the next command.
If the command is the last command in the pipeline, the object is displayed in the console.

Write-Output sends objects down the primary pipeline, also known as the "output stream" or the "success pipeline." To send error objects down the error pipeline, use Write-Error.

This cmdlet is typically used in scripts to display strings and other objects on the console.
However, because the default behavior is to display the objects at the end of a pipeline, it is generally not necessary to use the cmdlet.
For example, "get-process | write-output" is equivalent to "get-process".
## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>$p = get-process
PS C:\>write-output $p
PS C:\>$p
```

These commands get objects representing the processes running on the computer and display the objects on the console.
### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\>write-output "test output" | get-member
```

This command pipes the "test output" string to the Get-Member cmdlet, which displays the members of the String class, demonstrating that the string was passed along the pipeline.
## PARAMETERS

### -InputObject
Specifies the objects to send down the pipeline.
Enter a variable that contains the objects, or type a command or expression that gets the objects.

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).
## INPUTS

### System.Management.Automation.PSObject
You can pipe objects to Write-Output.
## OUTPUTS

### System.Management.Automation.PSObject
Write-Output returns the objects that are submitted as input.
## NOTES

## RELATED LINKS

[Tee-Object](.\Tee-Object.md)

[Write-Debug](.\Write-Debug.md)

[Write-Error](.\Write-Error.md)

[Write-Host](.\Write-Host.md)

[Write-Progress](.\Write-Progress.md)

[Write-Verbose](.\Write-Verbose.md)

[Write-Warning](.\Write-Warning.md)

