# Regular expressions

## Belangrijkste begrippen

- gewone karakters (`a`, `b`, `1`, `!`, `@`, ...)
- control characters (tab `\t`, newline `\n`, ...)
- quantifiers (`?`, `+`, `*`)
- anchor points (ankerpunten) (begin van zin, einde van zin, woord-grens, niet-woord-grens, ...)
- character classes (cijfer, letter, niet-cijfer, niet-letter, spatie, niet-spatie, ..., control karakter, ..., IsGreek, Nd, IsBoxDrawing, ...)
- ranges (zelfgedefinieerde character classes) (`[abc]`, `[^abc]`, `[a-z]`, `[a-z][0-9]`, ...)
- groups (matches) (b.v. (`((group) in een group))`)
- ascii of unicode

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

### Groups

`^Er zijn (\d+) leerlingen aanwezig$`.

zal de exacte zin `Er zijn 25 leerlingen aanwezig.` matchen en `25` opslaan als aparte group.

Standaard is er steeds 1 group : de gehele match.

Groups kunnen een naam meekrijgen:

`Er zijn (?<aantal>\d+) leerlingen aanwezig.`

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

## Globbing

Je mag regular expressions niet verwarren met **globbing**, zoals b.v.

```
ls *.md
mv index.htm? Index.html
```

> Globbing gebruik je typisch in een shell.
