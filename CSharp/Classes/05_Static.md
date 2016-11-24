# Static

`static` is een keyword dat voor de definities van **methods** en **variabelen** kan
gezet worden.

Een `static` method kunnen we gebruiken zonder we eerst een object moeten
maken. Bekende voorbeelden zijn :

- `Math.Round(...)` 
- `String.Join(...)`
- `Console.WriteLine(...)`
- `MessageBox.Show(...)` 

> Merk op dat b.v. `String`-class zowel `static` als niet-`static` methods heeft.
> `Math` en `Console` zijn dan weer classes met **enkel** `static`-methods.


## Een static method

```
public class TestStaticMethods {
  public static void EenStaticMethod() {
    Console.WriteLine("Ik ben een static method.");
  }
  
  public void EenGewoneMethod() {
    Console.WriteLine("Ik ben een gewone method.");
  }
}
```

Dit kunnen we nu zo gebruiken:

```
TestStaticMethods.EenStaticMethod(); // aangeroepen vanuit de class zelf
TestStaticMethods tsm = new TestStaticMethods();
tsm.EenGewoneMethod(); // aangeroepen vanuit een object v.d. class
```



## Een static variabele

Een (verder nutteloze) klasse die wel de werking van een **static field** 
AKA **static class variable** demonstreert:

```
public class InstantieTeller
{
  static private int aantalInstanties = 0;

  public InstantieTeller()
  {
      aantalInstanties++;
  }

  public string Serienummer
  { 
    get
    {
        return "INST" + aantalInstanties;
    }
  }
}
```

Hier wordt de variabele `aantalInstanties` als `static` gedefinieerd.
Dit wil nu zeggen dat de class `InstantieTeller` steeds maar 1 keer deze
variabele heeft, ongeacht hoeveel objecten we maken.

`aantalInstanties` hoort dus bij de **class** en niet bij de **objecten** die we
v.d. class maken.

In dit geval gebruiken we `aantalInstanties` dus om te tellen hoeveel keer
de constructor van `InstantieTeller` al is aangeroepen of m.a.w. hoeveel
objecten er al van de class `InstantieTeller` zijn gemaakt.

Een voorbeeldaanroep:

```
class Program
{
  static void Main(string[] args)
	{
		InstantieTeller i1 = new InstantieTeller();
		InstantieTeller i2 = new InstantieTeller();

		Console.WriteLine(i1.Serienummer);
		Console.WriteLine(i2.Serienummer);
  }
}
```

In dit voorbeeld maken we zeer veel `InstatieTeller`-objecten.
Elk object heeft zijn eigen variabele `serienummer` maar de variabele
`aantalInstanties` hoort bij alle objecten tegelijk of dus eigenlijk bij de
class.

> De compiler zal steeds foutmeldingen geven als `static` methods op de
verkeerde manier worden aangeroepen.


## In de praktijk

In de praktijk gebruiken we `static` voor een aantal belangrijke scenario's.

### Groeperen van methods

We willen een **method** onderbrengen in een class omdat methods groeperen
altijd een goed idee is. We willen ze echter gemakkelijk en overal kunnen
gebruiken.

Een voorbeeld is de `Math`-class met methods zoals `Math.Floor`, `Math.Round`, ...

### Een variabele maar 1 keer instantiëren

We willen een variable om 1 of andere reden maar **1 keer** definiëren. B.v.
voor een `Random`-object is dat een zeer goed idee. Immers, elke keer we een
nieuw Random-object maken, zal als *seed* de huidige tijd gebruikt worden,
met als gevolg dat kort op elkaar gemaakte Random-objecten allen dezelfde
Random-nummers zullen genereren.

B.v.

```
static class RandomGenerator
{
    static Random rndGen = new Random();
    static public int Next { get { return rndGen.Next(100); } }
}
```

### O.w.v. eerdere static-methods

Als we de method of variable willen gebruiken in een `static` method, moet de
gebruikte method of variable ook `static` zijn. Het is dan wel de vraag of het
noodzakelijk is dat de eerste method/variabele ook `static` is.

Een typisch voorbeeld is de `Main`-method van een Console-applicatie.

## Voorbeelden uit .NET en motivatie

In volgende voorbeelden zie je dat `static`, hoewel het meestal de uitzondering
is, soms toch zeer nuttig kan zijn.

- De `Math`-class heeft een hele hoop `static` methods.
- `Console.WriteLine(...)` is een static method.
- ...

De redenen hiervoor zijn:

- de functies is gemakkelijk aanroepbaar
- de functies staan toch gegroepeerd in een class (b.v. `Math`-functies, `Console`-functies)
- er is geen echte nood om een **object-toestand** bij te houden

