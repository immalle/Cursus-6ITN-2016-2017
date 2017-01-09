# Enkele commando’s

Echo :

- `echo Hello!`

Variabelen :

- `$groet = "Hello!"`
- `echo $groet`
- `echo $env:Path`

String-functie gebruiken :

- `$env:Path.split(";")`

Help :

- `get-help`
- `update-help`
- `get-command` : alle mogelijke commando’s en in welke module ze voorkomen

Aliases :

- `dir`
- `get-childitem`
- `cd`
- `set-location`

> `cd` en `dir` zijn alias’s van `get-childitem` en `set-location`

- `get-alias`
- `alias dir`
- `alias man`
- `alias`

- `alias %`
- `alias ?`

> `%` en `?` zijn ook 2 zeer krachtige alias’s

Datums:

- `get-date`

Powershell 'Drives' :

- `get-psdrive`
  - geeft een overzicht van alle ‘drives’ (niet alleen filesystem!)
  - interessant: `cd env:` (omgevingsvariabelen) en `cd hklm:` (registry)
  - `c:` of `cd c:` 

Process management:

- `start-process powershell -verb RunAs`
  - opent een powershell met Administrator-rechten
- `start-process powershell -argumentlist "-noprofile -command dir" -Verb runas`
  - voert `dir` uit met Administrator-rechten


Met `CTRL-C` of `CTRL-Break` kan je een lopend commando stoppen.
