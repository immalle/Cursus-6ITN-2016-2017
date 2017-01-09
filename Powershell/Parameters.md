# Parameters meegeven

Aan de help output is te zien welke parameters optioneel zijn en welke
parameter(s) als default wordt meegegeven.

Gewone help opvragen:

- `get-help get-help`

Voorbeelden (online) opvragen:

- `get-help get-help -examples`
- `get-help get-help -online`
- `get-help dir -examples`
- `get-help echo -examples`

> Merk op dat de alias `echo` gebruikt wordt maar de `Write-Output`-help getoond wordt

Gedetailleerde help:

- `get-help dir -detailed`
- `get-help update-help -detailed`

- `dir c:\ -recurse`

Help over allerlei onderwerpen:

- `get-help about*`
- `get-help about_aliases`
- `get-help about_operators`

Wildcards gebruiken:

- `get-help get*`
- `get-command get*`

Andere:

- `get-help get-member`
- `get-member -InputObject get-command -membertype Method`
- `get-help start-process`
