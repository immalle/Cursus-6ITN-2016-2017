# Uitvoer doorvoeren naar andere commando’s / alles is een object

Het pipe-symbool (|) wordt ook in de traditionele opdrachtprompt gebruikt om de
uitvoer van een commando door te sturen naar de invoer van een ander commando.
Vaak zijn er specifieke commando’s die heel nuttig kunnen zijn om achter de |
voor te komen, b.v. `more` (of `less`).

In Powershell is de in- en uitvoer niet puur op tekst gebaseerd maar wordt er
achter de schermen **met echte objecten** gewerkt. Zoals in object geöriënteerde
programmeertalen heeft elk object **methods en properties**.

> Powershell is dus een OO-shell!

Enkele interessante commando’s om te gebruiken achter een pipe:
- `gm`
- `where`
- `?`
- `sort`
- `group`
- `measure`
- `select`
- ...

b.v. `dir | measure`, `measure-object | gm`, ...

## Get-Member

Om b.v. een overzicht te krijgen welke methods en properties een object ondersteund:

- `measure | gm`
- `get-command | get-member`
- `dir | get-member`
- `get-date | gm`
- ...

Als je een commando met de default parameters (dus geen parameters!) opstart,
krijg je standaard slechts een aantal properties te zien, b.v. dir toont de
kolommen:

- Mode
- LastWriteTime
- Length
- Name

Maar met `dir | gm` zie je dat er nog vele andere properties zijn die we zouden
kunnen tonen.

## Select-Object

Select-Object (alias select) is een 'filter'-commando dat zich thuisvoelt
achter het |-symbool:

- `dir | select creationtime, lastwritetime, length, name`
- `get-command get* | select-object name, dll, module`
- ...

De parameter -Unique geeft bij gelijke properties er maximaal 1 weer.

- `get-process | select -Unique`
- `get-process | select name -Unique`

## Format-*

`Format-List`, `Format-Table`, `Format-Wide`, `Out-GridView` passen de weergave
aan:

- `dir | select creationtime, lastwritetime, length, name | format-list`
- `dir | select creationtime, lastwritetime, length, name | format-table`
- `dir | select creationtime, lastwritetime, length, name | format-wide`
- `get-command get* | select-object name, dll, module | format-wide`
- `get-command get* | select-object name, dll, module | out-gridview`
- `get-command get* | select-object name, dll, module | ogv`

## Object syntax

Door een commando tussen haakjes te zetten en er een property van te kiezen,
wordt alleen het resultaat terug gegeven:

- `(dir c:\).Name`
- `(get-date).Year`
- ...

Dit is handig om later in scripts te gebruiken, b.v. in combinatie met een If-
statement.

Op deze manier kunnen we b.v. ook van vele commando’s (niet van allemaal)
zien welke properties default worden getoond:

```
(dir).PSStandardMembers.DefaultDisplayPropertySet
```

Meer info: http://poshoholic.com/2008/07/05/essential-powershell-define-default-properties-for-custom-objects/)

## Where-Object

Met `Where-Object` (alias `where` of `?`) kan je resultaten filteren. 

Enkele afkortingen:

- gt
  - greather then
  - groter dan
- lt
  - less than
  - kleiner dan
- eq
  - equal
  - gelijk
- match
- cmatch
  - case sensitive match
  - hoofdlettergevoelig
- ...

Voorbeelden:

```
dir c:\ | ? LastWriteTime -gt 2008-01-01
get-verb | ? group -match 'common' | format-wide -AutoSize
```

## Verb-Noun syntax

Het is je waarschijnlijk al opgevallen dat commando’s de structuur 
`Verb`-`Noun` hebben. 

Deze verbs zijn ook nog eens opgedeeld in Groups.

- `Get-Verb`
- `get-verb | ? group -match 'common' | format-wide -AutoSize`


## Voorbeelden

Er zijn nog vele andere commando’s die zeer geschikt zijn om achter `|` te
zetten, zoals `group`, `measure`, ...

- get-process | gm
- get-process | fl *
- get-process | gm -membertype Method
- dir c:\ | sort-object LastWriteTime -Descending
- dir c:\ | sort-object LastWriteTime -Descending | ogv
- dir c:\ | measure-object
- dir c:\ | measure-object | gm
- (dir c:\ | measure).count
- Show-Command dir
- get-process | group name
- get-command -commandtype cmdlet | group verb | sort count -Descending
- get-command -commandtype cmdlet | group verb | sort count -Descending | select -First 10


