# Legende

- :hash: `x` : dit komt aan bod in hoofdstuk `x` van het handboek
- :pushpin: : dit zou je volledig moeten beheersen
- :rocket: : hier moet je momenteel op oefenen
- :checkered_flag: : dit komt aan bod op de volgende test
- :bangbang: : nog niet gevraagd op een test maar kan wel op het PW voorkomen
- :earth_africa: : externe link

# Allerlei

- [Begrippenlijst : Allerlei](Begrippenlijst/Allerlei.md)
- [Speciale karakters : naamgeving + ASCII-code](Begrippenlijst/SpecialeKarakters.md)
- Newline-karakters op verschillende platformen (Unix: `\n`, OSX: `\r`, Win: `\r\n`)
- http://www.markdowntutorial.com/

# Excel

- [Cell Formatting / Celweergave](Excel/CellFormatting.md)
- [Csv importeren en parsen](Excel/Csv.md)
- [Tabellen en draaitabellen (pivot tables)](Excel/Tables.md)
- [3D kaarten](Excel/3D_Charts.md)

# Word

- :earth_africa: [Non breaking space](http://wordribbon.tips.net/T013071_Inserting_a_Non-Breaking_Space.html)

# Git

- [Git commands die je zeker moet kennen](Git/Cmds.md)
- Automatisch closen van GitHub issues met `Fix #1` (https://help.github.com/articles/closing-issues-via-commit-messages/)
- gebruik van `y` op GitHub om links naar welbepaalde commit te maken
- grafisch overzicht met `gitk` (of `gitk -a`)

# Regular expressions

- RegEx tutorial : https://regexone.com/
- RegEx tester : http://regexr.com/
- [Overicht van de belangrijkste begrippen](Regex/Regex.md)
- [Regular expressions : belangrijkste begrippen a.h.v. een voorbeeld](Regex/RegexVoorbeeld.md)
- Zeer volledige tutorial : http://www.regular-expressions.info/tutorial.html
- [Voorbeeld in Powershell (ISE)](Regex/PowershellISE.md)

# CSharp

## Allerlei

- Parsen van command line argumenten (b.v. in https://github.com/vbrh-immalle/SharpShell/blob/eb935427bccd745b35b6ec05074c36fc3b089463/Program.cs)
- [String.IsNullOrEmpty vs exceptions](CSharp/StringIsNullOrEmptyVsExceptions.md)
- [Unicode karakters in C#](CSharp/Unicode.md)
- [Format strings](CSharp/FormatStrings.md)
- [Methodes aanroepen](CSharp/MethodesAanroepen.md)
- [Methodes : overloads](CSharp/MethodesOverloads.md)
- [Itereren over Lists](CSharp/IterateLists.md)
- [Attributen](CSharp/Attributen.md)
- [Exceptions](CSharp/Exceptions.md)
- https://learnxinyminutes.com/docs/csharp/

## Regex in CSharp

- [Eenvoudige Regular Expressions in C#](CSharp/RegexSimple.md)
- [Regular Expressions in C# met groups](CSharp/RegexGroups.md)

## Unittesting in CSharp

- Unittesting met MSTest en Directories en Files : https://github.com/vbrh-immalle/DirectoriesAndFileIO
- Unittesting en RegEx : https://github.com/immalle/UnitTestsVerbeteringTest1RegExCSharp

## LINQ

- [Extension Methods](CSharp/ExtensionMethods.md)
- [LINQ introductie](CSharp/LINQIntro.md)
- [LINQ voorbeelden](CSharp/LINQExamples.md)
- [LINQ `Count` met en zonder lambda expressie](https://dotnetfiddle.net/o5T9Dl)

## Dictionaries

- [Dictionaries : introductie a.h.v. `woordenTeller` en `AnalyseerZin`](CSharp/DictionaryIntro.md)
- :earth_africa: https://www.dotnetperls.com/dictionary
- toepassingen dictionary :
    - switch/case vermijden
    - mappings maken
    - https://github.com/vbrh-immalle/SharpShell/blob/18561c3d105e1adbb3871e346fcde7a6f28f15be/Program.cs#L110
    - http://stackoverflow.com/questions/2896715/dictionary-with-delegate-or-switch

## Classes

- [Access specifiers : `public`, `protected`, `private`](CSharp/Classes/01_ClassesAccessSpecifiers.md)
- [Properties](CSharp/Classes/02_Properties.md)
- [(Default) constructors](CSharp/Classes/03_Constructors.md)
- [Oef `Voertuig`](CSharp/Classes/03_OefVoertuig.md)
- [`this`](CSharp/Classes/04_This.md)
- [`static` methods en variabelen](CSharp/Classes/05_Static.md)

## Overerving

- [Inleiding](CSharp/Inheritance/01_Overerving.md)
- [Virtual en override](CSharp/Inheritance/02_VirtualOverride.md)
- [Abstract](CSharp/Inheritance/03_Abstract.md)
- [Overriden van `ToString`](CSharp/Inheritance/04_OverridenVanToString.md)
- [Base](CSharp/Inheritance/05_Base.md)
- [Constructors en overerving](CSharp/Inheritance/06_Constructors.md)
- [Polymorfie](CSharp/Inheritance/Polymorfie.md)
- [Polymorfie voorbeeld met WPF shapes](CSharp/Inheritance/PolymorfieShapes.md)
- Uitgebreid voorbeeld : https://github.com/vbrh-immalle/Traffic

zie ook: https://msdn.microsoft.com/en-us/library/67ef8sbd.aspx : C# Programming Guide

## Interfaces

- [Interface : introductie](CSharp/InterfacesIntro.md)

## Software Design

- [Voorbeeld bijhouden van een *program state* en gebruik van Hashmap (Dictionary)](CSharp/Voorbeelden/)


# HTML

- non breaking space `&nbsp;`
- [Font awesome en unicode](Webdesign/FontAwesomeUnicode.md)

# Javascript

- Google Apps Scripting (GAS) (https://www.google.com/script/start/)
- GAS : custom menu (https://developers.google.com/apps-script/guides/menus)
- regex in Javascript (https://developer.mozilla.org/nl/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec)
- qunit testing framework (https://qunitjs.com/)
- regex + qunit : https://github.com/vbrh-immalle/RegexQunitJavascriptTests
- [Voorbeeld: regex met grouping in GAS](Javascript/GASRegex.md)
- :checkered_flag: verband objecten en dictionaries

Oef. om te proberen in de Javascript terminal:

Vertrek van `blank.html`:

```
<html>
<head></head>
<body></body>
</html>
```

- :checkered_flag: [Oef. Ajax](Javascript/oef_ajax.md)
- [Oef. DomApi](Javascript/oef_domapi.md) (niet kennen)
- :checkered_flag: [Oef. event handlers](Javascript/oef_eventhandlers.md)
- :checkered_flag: [Oef. form uitlezen](Javascript/oef_form.md)
- :checkered_flag: [Oef. JSON](Javascript/oef_json.md) 

- :checkered_flag: [ClassList](Javascript/classlist.md)
- [Scrollspy](Javascript/scrollspy.md)
- :checkered_flag: higher order functions (map, reduce, filter, ...)

# VirtualBox

- [VirtualBox basisconfiguratie](VirtualBox/Basis.md)

# Linux

- :checkered_flag: [Linux basis-commando's](Linux/BasicCmds.md)
- :checkered_flag: [Linux advanced-commando's](Linux/AdvancedCmds.md)
- :checkered_flag: [Linux directory structuur](Linux/Directories.md)
- [Apt repositories en `.deb`-files](Linux/Apt.md)
- :checkered_flag: [PATH omgevingsvariabele](Linux/Path.md)
- [XFCE Window Manager tips](Linux/Xfce.md)

# Powershell

- :earth_africa: [Powerpoint Powershell 1 (OneDrive)](https://immalle-my.sharepoint.com/personal/hans_vanbroeckhoven_immalle_eu/_layouts/15/guestaccess.aspx?docid=0c14cc059872a48a9ba3a1770094870ea&authkey=ATA2fxjifPyXUGf0ESpCDjo)
- :earth_africa: [Powerpoint Powershell 2 (OneDrive)](https://immalle-my.sharepoint.com/personal/hans_vanbroeckhoven_immalle_eu/_layouts/15/guestaccess.aspx?docid=18ca1fe26a5df4164a6f2fc3508414de9&authkey=AXabqQuhTw5xtf9TFXw_1gg)
- [Installatie en controleren van de versie](Powershell/InstallatieVersie.md)
- :checkered_flag: [De Powershell ISE werkomgeving](Powershell/Werkomgeving.md)
- :checkered_flag: [Enkele commando's](Powershell/EnkeleCommandos.md)
- :checkered_flag: [Parameters meegeven](Powershell/Parameters.md)
- :checkered_flag: [Commando's combineren met `|` en de OOP-Shell](Powershell/Commandos.md)
- :checkered_flag: [Variabelen](Powershell/Variabelen.md)
- :checkered_flag: [Oef](Powershell/Oef)
- :checkered_flag: [Extra](Powershell/Extra)

# HTTP

- :checkered_flag: [Situering](Http/Situering.md)
- [Curl : CLI http client](Http/Curl.md)
- :checkered_flag: [Cookies analyseren met Fiddler en Wireshark](Http/CookiesFiddlerWireshark)
- :checkered_flag: [Http en Php analyseren met wireshark](Http/WiresharkHttpPhpAnalyse)
- [Tracking voor marketing-doeleinden](Http/TrackingMarketing.md)

# Web-applicaties met Php

- :checkered_flag: [Routes](Webapps/Routes.md)
- :checkered_flag: [Php Cookieclicker: cookies vs. sessions](https://github.com/vbrh-immalle/phpcookieclicker.git)
- :checkered_flag: [Php basics](https://github.com/vbrh-immalle/php-basics)
- :checkered_flag: [Php MySQL](https://github.com/vbrh-immalle/php-mysql)
- :checkered_flag: [Php forms](https://github.com/vbrh-immalle/php-forms)

# Web-applicaties met Python

- [Python versies](Python/PythonVersies.md)
- :checkered_flag: [Een simpele HTTP server (een directory hosten)](Python/HttpServer.md)
- [Python console](Python/PythonConsole.md)
- :checkered_flag: [Flask](Python/Flask.md)
- [MySQL](Python/MySQL.md)

# SQL

- :earth_africa: https://sqlbolt.com/
- :earth_africa: https://www.sololearn.com/Course/SQL/
- :earth_africa: [Powerpoint (OneDrive)](https://immalle-my.sharepoint.com/personal/hans_vanbroeckhoven_immalle_eu/_layouts/15/WopiFrame.aspx?docid=08a4815504fea42cab8bbc5a179409109&authkey=AZ1tj1ub6zErS16YElYWhxg&action=view)
- :checkered_flag: [SQL overzicht](SQL/sql.md)
- :checkered_flag: [SQL voorbeelden](SQL/voorbeelden.md)
- :checkered_flag: [SQL files (`.xlsx` -> `csv`)](SQL/dbfiles/)
- :checkered_flag: [Voorbeeld 1-op-1](SQL/voorbeeld-1-op-1.md)
- :checkered_flag: [Voorbeeld 1-op-veel](SQL/voorbeeld-1-op-veel.md)
- :checkered_flag: [Voorbeeld veel-op-veel](SQL/voorbeeld-veel-op-veel.md)

# Leerstof PW juni

- [Leerstof PW juni](leerstof_juni.md)

