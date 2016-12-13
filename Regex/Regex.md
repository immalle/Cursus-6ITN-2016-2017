# Regular expressions

## Belangrijkste begrippen

- gewone karakters (`a`, `b`, `1`, `!`, `@`, ...)
- control characters (tab `\t`, newline `\n`, ...)
- quantifiers (`?`, `+`, `*`)
- anchor points (ankerpunten) (begin van zin, einde van zin, woord-grens, niet-woord-grens, ...)
- character classes (cijfer, letter, niet-cijfer, niet-letter, spatie, niet-spatie, ..., control karakter, ..., IsGreek, Nd, IsBoxDrawing, ...)
- ranges (zelfgedefinieerde character classes) (`[abc]`, `[^abc]`, `[a-z]`, `[a-z][0-9]`, ...)
- groups (matches) (b.v. (`((group) in een group))`)
- escapen (met `\`)
- ascii of unicode

### Escapen

Sommige karakters hebben in een regular expression een bepaalde betekenis,
zoals:

- `.` : alle karakters
- `+` : de 1-of-meer-quantifier
- ...

Als je een *letterlijke* `.` nodig hebt, moet je escapen : `\.`.

### Ankerpunten

`^` of `\A` : de string moet hiermee beginnen
`$` of `\Z` : de string moet hiermee eindigen

### Quantifiers

- `?` : 0 of 1 keer
- `*` : 0 of meer keer
- `+` : 1 of meer keer

- `{2}` : 2 keer
- `{3,7}` : 3 tot 7 keer

### Ranges

`[abc]` wil zeggen : het karakter `a` of `b` of `c`

`[a-z]` wil zeggen alle letters van `a` tot `z`

Ranges kunnen ook geinverteerd worden:

`[^ab]` wil zeggen : niet `a` of `b`

Een range voor alle klinkers : `[aeiou]`.

### Voorgedefinieerde ranges (character classes)

- `\d` zijn alle cijfers
- `\D` komt overeen met `[^\d]`
- `\w` komt overeen met `[a-zA-Z0-9_]` (dus ook de underscore en getallen)
- `\W` komt overeen met `[^\w]`
- ...

`\s` kan je gebruiken voor spatie maar je kan even goed een letterlijke ` `
gebruiken. `\S` komt overeen met `[^\s]` : alles wat geen spatie is.

### Groups

`^Er zijn (\d+) leerlingen aanwezig$`.

zal de exacte zin `Er zijn 25 leerlingen aanwezig.` matchen en `25` opslaan als aparte group.

Standaard is er steeds 1 group : de gehele match.

Groups kunnen een naam meekrijgen:

`Er zijn (?<aantal>\d+) leerlingen aanwezig.`

## Groups met OR

`|` is de OF-operator. Je moet groupings gebruiken om ervan gebruik te kunnen
maken.

b.v.

```
^Er zit een (kat|hond) in de keuken.$
```

zal al volgende zinnen matchen:

- Er zit een (kat) in de keuken.
- Er zit een (hond) in de keuken.

Bovendien is `kat` of `hond` beschikbaar als group.

## Voorbeeld 1

```
[dh]et?
```

zal al volgende strings matchen: `de`, `det`, `he`, `het`

## Voorbeeld 2

```
h[aeiou]tt[aeiou]nt[aeiou]t
```

zal al volgende strings matchen:

- `hottontot`
- `hittontut`
- `huttantot`
- ...

## Voorbeeld 3

```
b[aou]{2}m
```

zal al volgende strings matchen:

- `baam`
- `boom`
- `buum`

## Voorbeeld 4

Alle strings die met een `.` eindigen:

```
\.$
```

zal al volgende strings matchen:

- `Dit is een zin.`
- `...`
- ...

## Voorbeeld 5

Alle strings waarin een berekening met `+` of `*` voorkomt:

```
\d+[\+\*]\d+
```

zal al volgende strings matchen:

- `375+445`
- `Het product 3*8 is 36.`

## Globbing

Je mag regular expressions niet verwarren met **globbing**, zoals b.v.

```
ls *.md
mv index.htm? Index.html
```

> Globbing gebruik je typisch in een shell.
