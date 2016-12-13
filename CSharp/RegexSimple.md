# Eenvoudig gebruik van Regular Expressions in CSharp

In zijn meest eenvoudige manier kunnen we gebruik maken van de static methods
van de class `RegEx` uit de namespace `System.Text.RegularExpressions`.

## Voorbeeld

We gebruiken
[een regular expression voor een nummerplaat](../Regex/RegexVoorbeeld.md).

https://dotnetfiddle.net/LC6Faz

## De method `IsMatch`

```
if(Regex.IsMatch("1-ABC-123", @"^\d-[a-zA-Z]{3}-\d{3}$"))
{
    Console.WriteLine("Geldige nummerplaat!");
}
```

## De method `Match`

Vanuit de `Match` kunnen we properties opvragen:

```
Match m = Regex.Match("1-ABC-123", @"^\d-[a-zA-Z]{3}-\d{3}$");

if(m.Success) {
	 Console.WriteLine("Het is een geldige nummerplaat!");
}

Console.WriteLine(m); // gebruikt de .ToString()-method
Console.WriteLine(m.Value);
Console.WriteLine(m.Index);
```

De `.Index`-property geeft de index waar de match matcht.
In dit geval op positie 0 wat normaal is als je `^` gebruikt.

> In dit geval zou de match op `.Index` 3 liggen:
> `Regex.Match("immalle", "al")`.
> Probeer dit zelf uit in de C# interactive console:

```
using System.Text.RegularExpressions;
var m = Regex.Match("immalle", "al");
m.Index
```

## De method `Replace`

Vervang alle cijfers (`\d`) door de string `"Z"`.

```
string s = Regex.Replace("1-ABC-123", @"\d", "Z");
Console.WriteLine(s);
```

## `RegEx` : `static` of gewone methods?

Het makkelijkst is om de `static`-methods van `Regex` te gebruiken:

```
var m = Regex.Match("Wij gaan naar immalle.", "im*alle");
```

Je kan ook een `RegEx`-object maken. Dit is vooral handig als je
(b.v. in een loop) de regular expression wil herbruiken.

```
var re = new Regex("im*alle");
var m = re.Match("Wij gaan naar immalle.");
```

## Overzicht v.d. members van `Regex`

De namespace `System.Text.RegularExpressions` heeft:

- een enum `RegexOption`, met waarden zoals
  - `RegexOption.None` : geen opties
  - `RegexOption.IgnoreCase` : hoofdletterongevoelig
  - `RegexOption.Singleline` : `.` matcht elk karakter, i.p.v. alles behalve `\n`
  - `RegexOption.Multiline` : `^` en `$` betekenen begin en einde van elke lijn i.p.v. hele string
  - ...
- de class `Match` waarin een resultaten van een regex-match in worden opgeslagen
- de class `MatchCollection` : een lijst van `Match`'s
- de class `Group` waarin het resultaat van een grouping (met `()`) in staat
- de class `GroupCollection` : een lijst van `Group`'s
- de class `RegEx` met als belangrijkste methods
  - `IsMatch(...)` : returnt een `bool`
  - `Match(...)` : returnt een `Match`-object met daarin de eerste match die
    gevonden werd
  - `Matches(...)` : return een `MatchCollection` met daarin een *lijst* van
    **alle** matches die gevonden werden
  - `Replace(...)` returnt een `string` met daarin een vervanging
  - `Split(...)` om te splitsen op basis v.e. regex, returnt een `string[]`

Zie de object browser of https://msdn.microsoft.com/en-us/library/system.text.regularexpressions.regex(v=vs.110).aspx voor meer details.
