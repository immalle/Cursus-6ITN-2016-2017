# This

In elke C#-class kunnen we `this` gebruiken.

Dit is een shortcut naar het huidige object.

In dit voorbeeld zijn er 2 variabelen met de naam `gewicht`:

- de class-variabele
- de parameter van de method `GokGewicht`

```
class Dier {
  private double gewicht;
  
  void GokGewicht(double gewicht) {
    if(gewicht > this.gewicht) {
      Console.WriteLine("Je gokte te hoog...");
    }
  }
}
```

Om het onderscheid te maken, gebruiken we `this`.

`this.gewicht` verwijst dus naar de class-variabele.

Je mag `this` steeds gebruiken maar meestal wordt het weggelaten als het
niet nodig is.

In dit voorbeeld zie je beide manieren gebruikt:

```
class Lamp {
  private bool brandend;
  
  void SchakelAan()
  {
    this.brandend = true; // hier gebruik we `this` hoewel het eigenlijk niet nodig is
  }
  
  void SchakelUit()
  {
    brandend = false; // hier gebruiken we `this` niet er is immers toch geen verwarring mogelijk
  }
}
```
