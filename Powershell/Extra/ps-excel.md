# Probleemstelling : processen in Excel

We willen met een Excel-tabel en een Excel-draaitabel (pivot table) de huidige
processen analyseren, b.v. om te kijken of er geen virus (b.v. een bitcoin
miner) draait.

Enkele tips:

- Converteer de output van `get-process` naar CSV
- Kunnen we een `output-gridview` gebruiken?
- Importeer de data 2 maal in 2 verschillende Excel-bladen
- Maak van 1 blad een tabel
- Gebruik 1 tabel als data-source voor een draaitabel


# Hulpmiddelen

- `Get-Help`
- http://www.techexams.net/forums/off-topic/41021-free-powershell-hands-exercises.html en Windows PowerShell Blog : Free PowerShell EBook

Ter info: mogelijk interessante Powershell-uitbreidingen:

- http://www.softwarefx.com/sfxSqlProducts/powerGadgets/
- https://stackoverflow.com/questions/9678982/powergadgets-alternatives
- https://github.com/PowerShell/PowerShellForGitHub

Ter info: mogelijk interessante tutorials:

- https://channel9.msdn.com/Blogs/trevor-powershell/Automating-the-GitHub-REST-API-Using-PowerShell


# Powershell

- `convertto-csv` om te importeren in Excel
- `get-process`
  - wat is de betekenis van NPM, PM, WS, VM, CPU, ... ?
  - https://superuser.com/questions/169386/what-do-the-headers-in-the-powershell-ps-output-mean
- `get-process | ogv` (`Output-GridView`)
  - filter op naam, b.v. alle `Chrome`-processen
  - sorteer op cpu-tijd gebruikt (`CPU`). Wordt dit correct gesorteerd?
  

# Powershell en Excel : CSV

- Gebruik `get-process` en `ConvertTo-Csv` voor alle gegevens over draaiende processen
- Importeer het `csv`-bestand in Excel (let op de delimiter!)

# Excel tables

- Ga naar `Data` en converteer naar een table
- Gebruik de dropdown-menus op de eerste rij om
  - te filteren
  - te zoeken
  - te sorteren
- Sorteer alle `chrome`-processen op cpu-tijd `CPU`. Is dit correct gesorteerd?

# Excel number formats

- Gebruik het custom number format `[<1000000]#.000," KB";[<1000000000]#.000,," MB";#.000,,," GB"`
  - Dit number format zet een aantal bytes (grofweg, o.w.v. 1000 i.p.v. 1024) om in KB, MB of GB
- Pas het aan zodat het een aantal KB omzet naar een aantal KB, MB of GB

# Excel Pivot tables

- Converteer de gegevens naar een **pivot table** (draaitabel)
- Maak enkele interessante *dashboards*, zoals:
  - Een dropdown-list (*filter*) waaruit `Company` kan gekozen worden. Je ziet in de
    draaitabel hoeveel processen (`Count of Product`) draaien van dit bedrijf.
  - Een filter voor de `Description` zodat je processen kan zoeken op basis van
    description (wat je ook te zien krijgt in de task manager / taakbeheer)
    
# Oplossingen

- sorteren in powershell afhankelijk van cultuurinstellingen (`,` vs `.`)
  - https://stackoverflow.com/questions/20426211/formatting-numbers-in-powershell-to-remove-the-for-numbers-1k
