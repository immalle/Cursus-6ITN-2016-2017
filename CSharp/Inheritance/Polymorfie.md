# Polymorfie

- Poly = veel
- Morf = vorm

Een polymorfe class kan dus veel vormen aannemen.

B.v. de abstracte class `Dier` kan de vorm aannemen van al haar
*kinderen* : `Varken`, `Paard`, ...

In code wil dit zeggen dat een variabele van type `Dier`, 
meerdere vormen kan aannemen:

```
Dier d = new Varken();

d = new Paard();

d = new Koe();
```

Dit is b.v. handig als we met een lijst van `Dier` moeten werken:

```
List<Dier> dierenVanJos = new List<Dier>();

dierenVanJos.Add(new Varken());
dierenVanJos.Add(new Paard());
// ...

for(Dier d in dierenVanJos) {
  Console.WriteLine(d.Gewicht); // polymorfisme in actie!
}
```


# OOP

We kunnen nu onze kennis van OOP vervolledigen.

Dit zijn de pijlers:

1. Encapsulatie
2. Overerving
3. Polymorfie

Polymorfie en overerving gaan natuurlijk hand in hand.

Polymorfie vermijdt een heleboel `if`'s.
