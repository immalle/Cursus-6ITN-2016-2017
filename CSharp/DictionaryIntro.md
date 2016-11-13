# Dictionaries

Dictionaries staan bekend onder verschillende namen:

- Maps
- HashMaps
- Key-Value-datastructuur
- ...

Het is een soort *mapping* tussen een **key** en een **value**, wat erg handig
kan zijn in bepaalde scenario's.

# Aanmaken

Een mapping tussen woorden en hoe vaak ze voorkomen:

```C#
Dictionary<string, int> woordTeller = new Dictionary<string, int>();
```

Een mapping tussen een `Persoon` en een URL van zijn/haar website:

```C#
class Persoon {
    string achternaam;
    string voornaam;
}

Dictionary<Persoon, string> websiteURLs = new Dictionary<string, string>();
```

# Element toevoegen

:construction:

# Itereren over Keys of Values

:construction:

# Itereren over KeyValuePair's

:construction:

# Voorbeelden

- https://dotnetfiddle.net/TEWeEX : woorden tellen 1 (met meerdere split-chars)
- https://dotnetfiddle.net/5Ktqsg : woorden tellen 2 (in aparte method)
