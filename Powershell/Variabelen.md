# Variabelen

Variabelen beginnen steeds met `$`. 

Alle geretourneerde objecten kunnen in Powershell ook aan een variabele worden toegekend.

```
$i = 3
```

Variabelen hebben een type. 
Het type kan steeds opgevraagd worden met de .Net-method `GetType()`. 

Je kan ook op een eerder *powershell-manier* het type opvragen, b.v. met 
`Get-Member` (`gm`). Bovendien krijg je dan ook alle members (eventuele methods,
properties, ...) te zien.

```
$i | gm
```

De waarde van een variabele kan worden weergegeven, simpelweg door de variabele
te typen als commando maar zal natuurlijk meestal gebruikt worden in samengestelde
commando's.

```
$i
$i 
```

Alternatief kan ook `write`, `echo` (aliasen van `Write-Output`) of
`Write-Host` gebruikt worden. Deze laatste kan met kleur werken.

Voorbeelden:

- `$i = 3`
- `$i.GetType()`
- `$j = $i + 8`
- `$j`
- `$vandaag = get-date`
- `$vandaag.GetType()`
- `write-host -foregroundcolor yellow (get-date)`
- `write-host -f red $vandaag`
- `write-host -f y -b darkcyan hello world!!`
- ...

# PS variabelen en omgevingsvariabelen

## Experimenten

- Wat is het verschil tussen `dir variable:` en `dir env:`?
  - Beiden gebruiken PSDrive's om gedefinieerde variabelen te verkennen
    maar `variable:` zijn de gewone variabelen terwijl `env:` alle
    omgevingsvariabelen bevat.
  - Probeer ook:
    - `get-variabele i` (geen `$`!)
    - `set-variabele a 3`
    - `$a`
    - `dir variable:a`
    - `cat variable:a`
- Zet de variablen `$myvar = 1` en `$env:myvar = 2`
  - probeer ze terug te vinden met `get-variable` en met `dir variable:` en `dir env:`
  - verwijder de variabelen met `remove-variable`
- Wat doet `alias | where Definition -LIKE *item*`?
  - Schrijf zelf een query om alle aliasen voor `Get-ChildItem` te tonen


