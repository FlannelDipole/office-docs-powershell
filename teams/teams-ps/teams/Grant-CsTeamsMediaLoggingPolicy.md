---
external help file: Microsoft.TeamsCmdlets.PowerShell.Custom.dll-Help.xml
Module Name: MicrosoftTeams
online version: https://docs.microsoft.com/powershell/module/teams/grant-csteamsmedialoggingpolicy
applicable: Microsoft Teams, Skype for Business Online
title: Grant-CsTeamsMediaLoggingPolicy
author: LeoKuhorev
ms.author: leokukharau
manager: saurk
schema: 2.0.0
---

# Grant-CsTeamsMediaLoggingPolicy

## SYNOPSIS

Assigns Teams Media Logging policy to a user, group of users or the entire tenant.

## SYNTAX

### Identity (Default)

```
Grant-CsTeamsMediaLoggingPolicy [[-Identity] <String>] [-PassThru] [[-PolicyName] <String>]
 [-MsftInternalProcessingMode <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GrantToTenant

```
Grant-CsTeamsMediaLoggingPolicy [-PassThru] [[-PolicyName] <String>] [-MsftInternalProcessingMode <String>]
 [-Global] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GrantToGroup

```
Grant-CsTeamsMediaLoggingPolicy [-PassThru] [[-PolicyName] <String>] [-MsftInternalProcessingMode <String>]
 [-Group] <String> [-Rank <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Assigns Teams Media Logging policy to a user, group of users or the entire tenant.
TeamsMediaLoggingPolicy allows administrators to enable media logging for users. When assigned, it will enable media logging for the user overriding other settings. After unassigning the policy, media logging setting will revert to the previous value.

## EXAMPLES

### EXAMPLE 1

```PowerShell
PS C:\> Grant-CsTeamsMediaLoggingPolicy -Identity 'KenMyer@contoso.com' -PolicyName Enabled
```

Assign Teams Media Logging policy to the user with the user principal name (UPN) "KenMyer@contoso.com".

### EXAMPLE 2

```PowerShell
PS C:\> Grant-CsTeamsMediaLoggingPolicy -Identity 'KenMyer@contoso.com' -PolicyName $null
```

Unassign Teams Media Logging policy from the user with the user principal name (UPN) "KenMyer@contoso.com".

### EXAMPLE 3

```PowerShell
PS C:\> Grant-CsTeamsMediaLoggingPolicy -Global -PolicyName Enabled
```

Assign Teams Media Logging policy to the entire tenant.

### EXAMPLE 4

```PowerShell
PS C:\> Grant-CsTeamsMediaLoggingPolicy -Global -PolicyName $null
```

Unassign Teams Media Logging policy from the entire tenant.

## PARAMETERS

### -Identity

Specifies the identity of the target user.
Acceptable values include:

Example: jphillips@contoso.com

Example: sip:jphillips@contoso.com

Example: 98403f08-577c-46dd-851a-f0460a13b03d

Use the "Global" Identity if you wish to set the policy for the entire tenant.

```yaml
Type: String
Parameter Sets: Identity
Aliases:
Applicable: Microsoft Teams, Skype for Business Online

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Enables passing a user object through the pipeline that represents the user being assigned the policy. By default, the Grant-CsTeamsMediaLoggingPolicy cmdlet does not pass objects through the pipeline.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Microsoft Teams, Skype for Business Online

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyName

Specifies the name of the policy to be assigned. The PolicyName is the policy identity minus the policy scope ("tag:"), e.g. a policy that has an identity of "Tag:Enabled" has a PolicyName of "Enabled".

Note that Teams Media Logging policy has only one instance that has PolicyName "Enabled".

If you set PolicyName to a null value, the command will unassign any individual policy assigned to the user.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Microsoft Teams, Skype for Business Online

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MsftInternalProcessingMode

Internal Microsoft use only.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Microsoft Teams, Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Global

When this cmdlet is used with `-Global` identity, the policy applies to all users in the tenant, except any that have an explicit policy assignment. For example, if the user already has Media Logging policy set to "Enabled", and tenant admin assigns "$null" globally, the user will still have Media Logging policy "Enabled".

```yaml
Type: SwitchParameter
Parameter Sets: GrantToTenant
Aliases:
Applicable: Microsoft Teams, Skype for Business Online

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi
Applicable: Microsoft Teams, Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf
Applicable: Microsoft Teams, Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsmedialoggingpolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsmedialoggingpolicy)
