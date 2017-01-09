# Variabelen

Variabelen beginnen steeds met `$`. Alle geretourneerde objecten kunnen in
Powershell ook aan een variabele worden toegekend. Variabelen hebben dus ook
een type. Het type kan steeds opgevraagd worden met de `GetType()`-method. Merk
op dat methods steeds worden aangeroepen met de ronde haakjes i.t.t. Properties
waarvoor dit niet nodig is.

De waarde van een variabele kan worden weergeven, simpelweg door de variabele
te typen als commando. Alternatief kan ook `write` (alias van `Write-Output`) of
`Write-Host` gebruikt worden. Deze laatste kan met kleur werken.

Voorbeelden:

- $i = 3
- $i.GetType()
- $j = $i + 8
- $j
- $vandaag = get-date
- $vandaag.GetType()
- write-host -foregroundcolor yellow (get-date)
- write-host -f red $vandaag
- write-host -f y -b darkcyan hello world!!
- ...
