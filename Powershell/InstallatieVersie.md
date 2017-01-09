# Versies / installatie

Powershell 2.0 staat standaard op Windows 7

Powershell 3.0 staat standaard op Windows 8 / Server 2012.

De versie kan opgevraagd worden met

```
$PSVersionTable.PSVersion
```

Om nieuwere versies te installeren:

`choco install powershell`

> Dit installeert ook het *Windows Management Framework* en bevat o.a.:

>   - WinRM (Windows Remote Management)
>   - WMI
>   - Windows Powershell x.0
