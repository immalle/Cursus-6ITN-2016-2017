# Regex voorbeeld

In wat volgt zullen we testen of een string een geldige nummerplaat bevat.

De string is een geldige nummerplaat als ze :

- begint met een cijfer
- gevolgd door een `-`
- gevolgd door 3 letters (en geen cijfers!)
- gevolgd door een `-`
- eindigt 3 cijfers

b.v.

```
1-ABC-123
```

Enkele **ongeldige** nummerplaten:

- `1-AB-123` : er is een letter te weinig
- `1-AB1-234` : 1 v.d. letters is een cijfer
- `pre 1-ABC-123` : de string begint met iets anders
- `1-ABC-123 post` : de string eindigt met iets anders

De regular expression:

```
^\d-[a-zA-Z]{3}-\d{3}$
```

- `^` en `$` zorgen dat er niets voor of achter de match mag staan
- `\d` staat voor een *digit* : een cijfer
- `\d{3}` gebruikt `{3}` als quantifier om 3 cijfers te matchen
- `[a-zA-Z]` gebruikt 2 ranges (`a-z` en `A-Z`) om alle letters aan te duiden
- `[a-zA-Z]{3}` matcht met exact 3 letters

## Over karakter classes in een regex

Let op:

- `\d` is digit en `\D` non-digit (of dus `[^\D]`)
- we kunnen hier niet `\w` gebruiken omdat dat overeen komt met `[A-Za-z0-9_]`
  (waar ook cijfers en de underscore inzitten)
- `\w{3}` kunnen we hier dus **niet** gebruiken

## De betekenis van een karakter in een regex

Een karakter heeft niet altijd dezelfde betekenis.

B.v. in

```
^\d-[a-zA-Z]{3}-\d{3}$
```

komt de `-` (dash) op 2 manieren voor:

- als te matchen karakter
- om een range aan te duiden

- `-[abc]` wil zeggen dat naar een string `-a`, `-b` of `-c` gezocht wordt
- `[a-z]` wil zeggen dat er een letter van `a` tot `z` gezocht wordt

Zo heeft ook `^` binnen een range een andere betekenis, nl. die van `NOT`.

- `[^abc]` wil zeggen : alles behalve het karakter `a`, `b` of `c`
- `^[abc]` wil zeggen : de string moet met een `a`, `b` of `c` beginnen
