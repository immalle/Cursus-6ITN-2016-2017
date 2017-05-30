# Powershell: eenvoudige opgaven

- Wat leert het commando `Get-PSProvider` je? Let op de kolom `Drives`.
  - gebruik `cd` en `dir` om deze *drives* te exploreren
  - Verklaar wat `alias cat` returnt en gebruik het om de inhoud van enkele
    powershell-functies te tonen

- De commando's `pushd` en `popd` bestaan ook in de meeste Linux-shells. Ze
  gebruiken een **Stack**-datastructuur om te navigeren tussen verschillende
  directories. Werkt dit in powershell ook met *drives* zoals `Alias:` en
  `Function:`?

- Maak de functie `SayHello`. De functie doet enkel `echo hello`.
  - `function SayHello() { echo hello }`
  - kan je de functie terugvinden in de lijst met functions?
  - is deze functie ook beschikbaar in een ander powershell-venster?
  - bestaat op jouw systeem de file waar de `$profile`-variable naar verwijst?
    - controleer met `echo $profile` of gewoon `$profile`
    - zoniet, bewerk de file en voeg de `SayHello`-functie hier toe. Wat is het gevolg?

- Waar wijst de alias `man` naar?
  - wat voor iets is `help`?
- Hoe kan je de inhoud van een functie laten zien?

- Waar wijst de alias `measure` naar?
- Waar wijst de alias `dir` en `ls` naar?
- Toon met `get-command -verb` alle commando's die het werkwoord `measure` gebruiken
- Toon de voorbeelden van het commando `measure-object`

- Voer `get-process | gm` of `get-process | get-member` uit. Kan je hieruit
  afleiden wat de belangrijkste kolommen (properties) zijn?

# Powershell queries

- Schrijf een query die de grootte van het kleinste en het grootste bestand in
  de huidige directory toont
  - Toon ook de som van de groottes
- Schrijf een query die van alle chrome-processen de `WorkingSet`-memory, de
  `CPU`-tijd en de `VirtualMemorySize` toont
  - Toon de som van al deze getallen (tip: gebruik `measure`)


# opl

- toon grootste file: `dir | where Length -eq (dir | measure -property length -Maximum).Maximum`
- `dir | measure length -Maximum -Minimum`
- `dir | measure length -Sum`
- `get-process | where Name -EQ chrome | select -Property WorkingSet, cpu, VirtualMemorySize | measure VirtualMemorySize -Sum -Maximum -Minimum -Average` 
