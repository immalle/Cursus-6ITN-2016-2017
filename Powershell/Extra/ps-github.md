
# Probleemstelling : github commits van al je repositories in Excel

We willen een Excel-bestand met daarin alle commit-beschrijvingen van
al je eigen repositories.

De tabel moet dus volgende kolommen hebben:

- De naam van een repository
- De datum van een commit
- De beschrijving van een commit

TIPS:

- Gebruik de GitHub API (json-output) (zoek op developer.github.com de juiste URL's)
- Gebruik `Invoke-RestMethod` en `ConvertTo-CSV`
- Importeer CSV in Excel

# Authenticatie met personalized token

```
$hdr=@{Authorization="token " + $GITHUB_TOKEN}
```
