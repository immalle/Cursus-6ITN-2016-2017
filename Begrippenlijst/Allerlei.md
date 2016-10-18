# OS

Operating System AKA besturingssysteem

Voorbeelden:

-   Windows 7
-   Windows 10
-   Windows Server 2013
-   Ubuntu 16.04
-   Android 6.0
-   Mac OS X 10.11

Zowel Ubuntu als Android maken gebruik van een Linux-kernel.
Ook Mac OS X gebruikt een Linux-achtige kernel (Darwin).

OS-pakketten zoals voornoemde voorbeelden bevatten meestal naast de kernel ook
nog heel wat hulpprogramma's (`.exe`'s, b.v. `notepad` wat op (bijna) elke Windows-machine aanwezig is)
en libraries (`.dll`'s, bibliotheken, zoals het **File Open Dialog** dat je in de meeste
programma's terugvindt).

# user-profile-directory

De directory waar b.v. Windows alle persoonlijke files standaard opslaat, b.v. `C:\Users\gebruikersnaam`

# user-account bij een online web-service

Soms kunnen user-accounts van verschillende web-services **gekoppeld** worden

# chrome-profiel (gmail-profiel)

# extensie

-   De laatste letters van een bestandsnaam, achter de `.`.
-   Ze bepalen met welke programma's het operating system het bestand moet openen.
-   Het zegt iets over de inhoud van het bestand.

# zip-bestand

Een gecomprimeerde map, hoewel er niet verplicht een map in aanwezig is.
Eigenlijk dus een verzameling bestanden die in een soort **archief** worden
verzameld in 1 bestand. Gewoonlijk worden de bestanden ook **gecomprimeerd** zodat
ze in het archief minder plaats in beslag nemen.
Andere archiverings-formaten zijn b.v. `.tar.gz`, `.7z`, `.rar`, ...

# exe-bestand

Uitvoerbaar bestand. Meestal in machine-code voor het juiste OS en CPU, b.v.

-   **Windows** en **x64**
-   **Linux** en **x86**

Soms maken `.exe`'s gebruik van een VM (Virtual Machine) zoals de
DotNet-runtime. Een ander voorbeeld van een dergelijke VM is de JVM (Java
Virtual Machine). (Opgelet: hier wordt iets anders mee bedoeld dan
virtualisatie-software zoals VirtualBox.)

# dll-bestand

In een DLL-bestand zit (net als in een EXE-bestand) **uitvoerbare** code.

Een Dynamically Linked Library wordt (dynamisch) in het geheugen geladen als een
proces de (uitvoerbare) code nodig heeft. Verschillende **processen** kunnen tegelijkertijd
de code benaderen.

Uiteindelijk wordt er met DLL's op 2 geheugen bespaart:

-   een (draaiend) proces zal minder RAM geheugen nodig hebben
-   een `.exe`-file moet minder groot zijn omdat een deel van de code uit de DLL's
    zal gehaald worden

De **proces-space** in het geheugen is normaal gezien **read-only**, zodat het geen
kwaad kan dat processen samen dezelfde RAM-locatie gebruiken.

# Proces / Programma

Met een programma wordt meestal een software-pakket bedoeld of de executabble
(`.exe`-extensie in Windows) waarmee dat pakket kan opgestart worden. Sommige
programma's zitten helemaal vervat in het `.exe`-bestand maar grotere
programma's gebruiken ook `.dll`-files uit allerlei subdirectories of de
systeemmap (b.v. `C:\Windows\System32`).

Processen zĳn ****draaiende**** programma's. 1 programma kan meerdere keren (als
verschillende processen) in het geheugen geladen zĳn. Met een tool als Process
Hacker (of zelfs de standaard Task Manager) kan je kijken welke processen actief
zijn en hoeveel geheugen ze in beslag nemen.

# RAM-geheugen

In gewone PC's is er maar 1 soort RAM geheugen, typisch b.v. 4, 8 of 16Gb.
Dat geheugen wordt zowel gebruikt om :

-   draaiende processen (uitvoerbare code) in bij te houden : de uitvoerbare code
    van het programma moet in het RAM-geheugen zitten voordat elke instructie naar
    de CPU kan worden gestuurd
-   data in op te slaan : b.v. de gegevens die op een bepaald moment in een
    Word-document zichtbaar zijn, of de inhoud van een tekstbestand in een
    tekst-editor

Wat zou er b.v. moeten gebeuren als je een 8Gb groot tekstbestand opent op een
PC met maar 4Gb geheugen? (Antwoord: dit is niet mogelijk tenzij het programma
zo geschreven is dat het tussendoor de harde schijf zal gebruiken.)

RAM-geheugen wordt op 2 manieren gebruikt:

-   Elk proces heeft zijn eigen **proces-space** of geheugenruimte waar het in draait.

In principe is dit geheugen read-only (virussen maken soms gebruik van het feit
dat ze live het RAM-geheugen waar de programma-instructies staan, aanpassen).

-   De **data** die elk proces gebruikt, zit in andere delen van het RAM-geheugen waar

het dan meestal read/write-rechten heeft. Het is de verantwoordelijkheid van het
OS om dit in goede banen te leiden.

Het systeem waarbij geheugen zowel voor **code**- als voor **data**-space wordt
gebruikt heet ****von Neumann architectuur****.
Er bestaan systemen (b.v. de PIC microcontrollers) die aparte geheugenchips
gebruiken voor **code** en **data**. Dit noemt men de ****Harvard architectuur****.

Kijk b.v. op <http://www.microcontrollerboard.com/pic_memory_organization.html> en
verklaar het gebruik van de 3 soorten geheugen die daar gebruikt worden. (TIP:
een microcontroller maakt geen gebruik van een extern opslagmedium zoals een
harde schijf of een SD-kaart.)

Zie eventueel ook <https://en.wikipedia.org/wiki/PIC_microcontroller> en
<http://akizukidenshi.com/download/PIC16F84A.pdf>

De micro-controller die de populaire Arduino's gebruiken is de
<http://www.atmel.com/devices/atmega168.aspx>.

# parsen

Het omzetten van **rauwe** data naar informatie met (meer) structuur.
Programma's verwerken informatie en de INPUT voor een programma is vaak **rauwe
data**.
Eens de data **geparset** is, begrijpt het programma de structuur van de data veel
beter en kan het programma de juiste OUTPUT voorzien.
B.v. een mail is eigenlijk een gewoon tekst-bestand maar na parsen van de
headers, is gemakkelijk op te vragen wie de zender, ontvanger, ... is

# IDE

Integrated Development Environment

Een geintegreerde ontwikkelingsomgeving waarin broncode kan geschreven worden
maar ook uitgevoerd en waar een zekere vorm van **project-management** aanwezig is.
Voorbeelden:

-   Visual Studio
-   Eclipse
-   ...

Notepad++ is geen IDE maar een simpele **text-editor**.
Een IDE kan meestal ook als gewone tekst-editor gebruikt worden maar dan gebruik
je niet de volledige functionaliteit van de IDE.

# directory-structuur

De hiërarchie van mappen op schijf.
Vbdn. van dingen met een eigen, typische directory-structuur:

-   de standaard mappen in je user-profile-directory, zoals `Mijn Documenten`,
    `Mijn afbeeldingen`, ...
-   een Visual Studio-project
-   een website waarin verschillende subdirectories zoals `images`, `styles` en
    `scripts` gebruikt worden
-   de xml-files in een `.docx`-bestand (na het uitpakken van de gezipte file of
    gecomprimeerde map)
-   `C:\Windows\` bevat heel wat bestanden en mappen die een onderdeel zijn van
    het besturingssysteem. Je mag niet zomaar die namen wijzigen of je OS zal niet
    meer goed werken
-   `C:\Program Files\` is de standaard locatie waar programma's geïnstalleerd
    worden, `C:\Program Files (x86)` wordt soms nog gebruikt voor (oudere) 32-bit
    programma's

# HyperText

Tekst met hyperlinks

# HTML

HyperText Markup Language

Een opmaaktaal (markup language) voor HyperText

# HTML-element / HTML-tag

b.v. `<h1>`, `<img>`, ...

Sommige elementen (zoals `<img>`) hebben geen sluitingstag.

Zie ook <https://www.w3.org/standards/webdesign/>

# HTTP

HyperText Transfer Protocol

https is ook nog secure (veilig, ge-encrypteerd)

Zie ook: HTTP/1.1 (versie 1.1): <https://tools.ietf.org/html/rfc7230>

Sinds mei 2015 bestaat er ook HTTP/2 (versie 2): <https://tools.ietf.org/html/rfc7540>

# FTP

File Transfer Protocol

Zie ook: <https://tools.ietf.org/html/rfc959>

# URL

Uniform Resource Locator
Een volgens een standaard eengemaakte, uniforme locator voor resources.
Resources kunnen allerlei dingen zijn zoals files, mail-adressen, ...
Een URL zegt dus waar we iets kunnen vinden.
Voorbeelden: 

-   `http://www.google.be` (de resource is een website)
-   `ftp://ftp.belnet.be` (de resource is een FTP-site)
-   `http://www.immalle.be/immalle/images/logo.jpg` (de resource is een afbeelding
    op een webserver)
-   `mailto:hans.vanbroeckhoven@immalle.be` (de resource is een e-mail-adres)
-   `file:///C:/Program%20Files/` (de resource is een directory op een
    Windows-machine, de `%20` is de **URL encoded** versie v.d. spatie)

Zie ook: <https://www.ietf.org/rfc/rfc1738.txt>
Een URL is een vorm van een URI: <https://tools.ietf.org/html/rfc3986>

# CDN

Content Delivery Network

Algemeen:

Netwerk van servers in data-centers op verschillende geografische locaties zodat
de dichtsbijzijne (meestal de snelste) verbinding automatisch kan worden
gekozen.

Specifiek voor websites:

Veel websites gebruiken dezelfde CDN-links (b.v.
<https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js>) zodat de cache
van de webbrowser deze file vaak al bevat wat er voor zorgt dat deze file niet
elke keer opnieuw moet gedownload worden.

# OOP

Object Oriented Programming, object georienteerd programmeren

Een programmeertechniek waarbij vaak **classes** gebruikt worden als **sjabloon** om
**objecten** te maken.

Het is een uitbreiding op **procedureel programmeren** waarbij enkel procedures
(functies, methods) gebruikt worden. Procedureel programmeren is op zijn beurt
een evolutie op het gebruik van **GOTO**-statements (waarmee naar willekeurige
plekken in de code kan gesprongen worden).

Voorbeelden:

-   C, Pascal, Go zijn procedurele talen.
-   .NET, Java en Ruby zijn OOP-talen of -frameworks.
-   Sommige talen ondersteunen OOP maar kunnen ook meer zoals C++, Python, ...
-   GOTO werd hevig gebruikt in de oorspronkelijke BASIC-varianten en nog steeds
    in b.v. `.BAT`-bestanden. (C en Go ondersteunen nog steeds goto!)
-   Assembler (assembly-code) leunt het dichtst aan bij machine-taal en maakt ook
    veelvuldig gebruik van GOTO-achtige instructies (JUMPs)

Tegenwoordig is ook **functioneel programmeren** terug in opmars met talen zoals
Haskell, F#, clojure, ...

In javascript kan je eveneens multi-paradigmaal programmeren.

# Constanten, variabelen, functies

b.v. in javascript:

<!-- This HTML table template is generated by emacs 24.5.1 -->
<table border="1">
  <tr>
    <td align="left" valign="top">
      &nbsp;constanten&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;Math.PI&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;variabelen&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;window.screenX&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
  <tr>
    <td align="left" valign="top">
      &nbsp;functies&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
    <td align="left" valign="top">
      &nbsp;console.log&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </td>
  </tr>
</table>

> `window.screenX` is een **read-only** variabele

Al deze dingen behoren tot een object : `Math`, `window` of `console`.
`window` is het globale object want alle constanten, variabelen en functies van
`window` zijn beschikaar in de Chrome Console.

# WPF-Control

Een WPF-Control is een besturingselement dat gebruikt in Microsoft's WPF
(Windows Presentation Framework). Voorbeelden zijn Labels, Buttons,
Dropdown-boxes, ...

Een WPF-Control is een **class** (OOP-term).

# XAML

Een XML-formaat voor het beschrijven van User Interfaces in WPF.

# Properties (van WPF-Controls)

# Coördinatensysteem

Voor computer graphics wordt meestal het assenstelsel gebruikt waarbij:

-   de X-as bovenaan het scherm ligt, een horizontale richting heeft en de zin van
    links naar rechts is
-   de Y-as links op het scherm ligt, een verticale richting heeft en de zin van
    onder naar boven is

Coördinaat (0,0) is daarom de linkerbovenboek.
Coördinaat (1024,768) is de rechter-onderhoek (bij een schermresolutie van
1024x768 pixels).
