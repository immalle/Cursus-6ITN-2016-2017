# Powershell

- https://github.com/immalle/Cursus-6ITN-2016-2017#powershell
- zie google form

# Linux

- https://github.com/immalle/Cursus-6ITN-2016-2017#linux

# SQL

- https://github.com/immalle/Cursus-6ITN-2016-2017#sql
- https://immalle-my.sharepoint.com/personal/hans_vanbroeckhoven_immalle_eu/_layouts/15/guestaccess.aspx?docid=08a4815504fea42cab8bbc5a179409109&authkey=AZ1tj1ub6zErS16YElYWhxg
- https://sqlbolt.com/
- https://www.sololearn.com/Course/SQL/

Je mag steeds MySQL Workbench gebruiken.
Je moet wel in staat zijn om de SQL-code te exporteren en "op te kuisen".
Weet b.v. wat `USE {databasename}` doet.

Je kan je verwachten aan:

- simpele queries (`SELECT`, `WHERE`, ...)
- queries met joins (verschil `LEFT` en `INNER`, ...)
- implementeren in MySQL van tabellen (1-op-1, 1-op-veel, veel-op-veel)
- user-rechten beheren van MySQL
- indexes en referentiële integriteit

Je moet ook code die gebruik maakt van een SQL-database kunnen aanvullen.
De voorbeelden die we in de klas besproken hebben zijn Php PDO en Python mysql-connector.


# HTTP protocol

- https://nl.wikipedia.org/wiki/Lijst_van_HTTP-statuscodes
- https://github.com/immalle/Cursus-6ITN-2016-2017#http


Zorg ervoor dat je weet:

- wat er zoal in een HTTP header te vinden is, zowel bij requests als responses
- dat HTTP een *stateless* protocol is en we dus extra dingen nodig om *state* (toestand) bij te houden
	- cookies
	- sessions (b.v. `$_SESSION`-variabele in Php)

Doe ook experimenten:

- schrijf enkele forms waarvan de action naar http://httpbin.org of http://requestb.in/ gaat
- schrijf je eigen rudimentaire versie van http://requestb.in/ met b.v. Php of Python (Flask)
- gebruik `curl` of `invoke-webrequest`/`invoke-restmethod` om op de CLI HTTP-requests te construeren
  en de responses te bestuderen

Je kan je verwachten aan enkele theoretische of inzichtelijke vraagjes.

# Webapplicaties

URL's:

- routes
- parameters via GET
- parameters via POST (ook inhoud van Body is belangrijk)


# Php

Voornamelijk gebruikt om de principes van HTTP-protocol uit te testen.
Zorg dat je de `$_GET`, `$_POST` en `$_SESSION` superglobals goed kan gebruiken.

- https://github.com/immalle/Cursus-6ITN-2016-2017#web-applicaties-met-php


# Javascript

- basissyntax, event listeners koppelen, ... (leerstof vorig jaar)
- arrow-functies en higher order functions (forEach, map, filter, reduce, some, every)
- XmlHttpRequest
- `localStorage` en `sessionStorage`
- cookies (nog te zien of herhalen)
- classList 
