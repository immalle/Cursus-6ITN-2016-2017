# Regular Expressions in CSharp met groups

## Groups

Een regex zoals `im*alle` heeft 1 group : de gehele match.

Een regex zoals `i(m*)al(le)` heeft 3 groups :

- de gehele match
- `(m*)` : het aantal `m`'s (kan `0` zijn)
- `(le)` : de `le`.

## Voorbeeld

We zullen deze string testen:

```
"120 jongens en 180 meisjes gaan naar immmmalle. Ga jij ook naar immalle?"
```

met deze regular expression:

```
@"(\d+) jongens en (\d+) meisjes gaan naar (im*alle)"
```

> Vergeet in C# `@` niet te gebruiken om de backslashes te escapen.
> Een andere manier zou zijn
> `"(\\d+) jongens en (\\d+) meisjes gaan naar (im*alle)"`.

Deze regular expressions heeft :

- 3 groups (eigenlijk 4 als we de match in zijn geheel meetellen!)
- de eerste group : 1 of meer cijfers `(\d+)`
- de tweede group : 1 of meer cijfers `(\d+)`
- de derde group : het woordje `immalle` of `immmalle` (afhankelijk
  hoeveel m's er werkelijk geschreven werden).

> Zelfs `ialle` (zonder `m`) zal matchen omdat we `*` als *quantifier* gebruikt
> hebben. `im{1,5}alle` zou alles met 1 t.e.m. 5 `m`'n matchen.

## Groups met een naam

**Eventueel** kan je een group een naam geven met de `(?<naam>)`-syntax:

```
var ms = Regex.Matches("Wij gaan naar immmmalle. Ga jij ook naar immalle?", "i(?<aantalm>m*)al(le)");
```
De grouping werd hier `aantalm` genoemd.

Als we itereren over de `Group`s zullen eerst de genummerde komen en pas daarna
de groups met een naam.

```
foreach(Group g in ms.Groups) {
    Console.WriteLine(g);
}
```
