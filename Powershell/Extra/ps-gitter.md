# Probleemstelling : chatbox in Excel

We willen alle chatberichten van de 6ITN-chatbox in Excel, liefst met
verschillende kolommen voor datum, gebruikersnaam en bericht.

Enkele tips:

- log in op https://developer.gitter.im/ en noteer je eigen token op de API te kunnen benaderen
- check de API, b.v. op https://developer.gitter.im/docs/rooms-resource
- je kan b.v. (via npm) `gitter-export-room` installeren maar eigenlijk is dit maar een kleine wrapper rond een REST-request
  en je kan dus even goed `curl` of `invoke-restmethod` gebruiken
- met de `Header`-parameter van `invoke-restmethod` kan je het *Bearer*-token van Gitter meegeven
- converteer en **filter** met powershell de JSON-data naar CSV en importeer in Excel


# Oplossing

## Authenticatie 

```
$GITTER_TOKEN = "abcdefghijklmnopqrstuvwxyz"

$hdr=@{Authorization="Bearer " + $GITTER_TOKEN}
```

Authenticatie gelukt?

```
invoke-restmethod https://api.gitter.im/v1/user -Headers $hdr
```

## Lijst met rooms

Verkrijg lijst met rooms:

```
$gitterrooms = invoke-restmethod https://api.gitter.im/v1/rooms -Headers $hdr
```

Toon de lijst:

```
$gitterrooms | ogv
```

Of toon enkel de naam, aantal users en id:

```
$gitterrooms | select name, userCount, id
$gitterrooms | select name, userCount, id | where name -like *chatbox*
```

Kan je tellen tot hoeveel kamers je toegang hebt met powershell?

## Specifieke room

A.h.v. de `id` van de room, kan je nu meer info over de room opvragen:

```
$roomid = "abcdefghijklmnopqrstuvwxyz"

$roominfo = invoke-restmethod https://api.gitter.im/v1/rooms/$roomid -Headers $hdr
```

Welke users er in zitten:

```
$roomusers = invoke-restmethod https://api.gitter.im/v1/rooms/$roomid/users -Headers $hdr
$roomusers | ogv
```

En de laatste 100 berichten:

```
$roommessages = invoke-restmethod https://api.gitter.im/v1/rooms/$roomid/chatMessages -Headers $hdr
$roommessages | select sent, text, fromUser | ogv
```

Zie https://developer.gitter.im/docs/messages-resource voor meer info, b.v. of pagination.
