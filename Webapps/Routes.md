# Routes

## Microframeworks

Microframeworks zijn vaak herkenbaar aan de gemakkelijke manier waarop
routes kunnen samengesteld worden:

- http://flask.pocoo.org/docs/0.12/quickstart/ (Python)
- http://www.sinatrarb.com/intro.html (Ruby)
- https://github.com/NancyFx/Nancy/wiki/Defining-routes (.Net)
- ...

Er wordt simpelweg een **method** gedefinieerd die een route afhandelt. Ook
de HTTP-methods (`GET`, `POST`, ...) zijn onmiddellijk herkenbaar.

## Php

Php werkt traditioneel door `.php`-files in bepaalde directories te zetten.

Routes definiëren komt dan dus neer op directories maken waarin een
`index.php` wordt geplaatst. (Uiteraard kan de file ook een andere naam
hebben maar dan eindigt de URL niet op een directory (`/`).)

## MVC-frameworks

Hier wordt meestal gebruik gemaakt van object georiënteerde technieken
waarbij er typisch classes zijn die een bepaalde rol vervullen:

- `Model` : een class die de *business-objecten* voorstelt, komt vaak
  overeen met de tabellen uit een database
- `View` : een template waarin variabelen gebruikt kunnen worden
- `Controller` : handelt webrequests af en bepaalt dus mee de **routering**
