# Path

## `Printenv`

`printenv` toont alle omgevingsvariabelen van de shell.

## `echo $PATH`

`PATH` is een zeer belangrijke.

`echo $PATH` toont enkel de inhoud van `$PATH`.

Het is een opsomming van directories, telkens gescheiden door een `:`.

## `which`

`which lsb-release` toont in welke PATH-directories de executable `lsb-release` gevonden is.

> Probeer b.v. ook `which vi`, `which ls`, `which mkdir`, ...

## Hoe bestendigen?

Voeg dit toe in `.zshrc` (of een ander user-specifiek opstart-script zoals `profile`, `.bashrc`, ... afhankelijk van welke shell)

```
export PATH=/home/imma/bin/:$PATH
```

De map `/home/imma/bin` staat nu altijd in het PATH.
De executables kunnen overal uitgevoerd worden.

