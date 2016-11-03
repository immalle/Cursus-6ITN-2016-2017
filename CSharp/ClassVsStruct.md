# Class vs Struct


```
struct Persoon {
  string naam;
  int leeftijd;
}

struct Woonplaats {
  string postcode;
  string gemeente;
}
```

De velden zijn default `public`.

## private variabele in struct

```
struct Woonplaats {
  string postcode;
  private string gemeente;
}
```

Nu is `gemeente` enkel binnen methods van de struct `Woonplaats` zelf
bereikbaar!

```
struct Woonplaats {
  string postcode;
  private string gemeente;

  void PrintGemeente() {
    Console.WriteLine(" PrintGemeente: " + gemeente);
  }
}
```

> `private` velden in een struct zijn **zeldzaam**!
> We leggen het alleen maar uit om de class-bouwtechniek uit te leggen.

