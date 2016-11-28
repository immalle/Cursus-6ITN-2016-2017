# Itereren over een lijst getallen

Gegegen:

```
private static List<int> numbers = new List<int>{ 1, 2, 3};
```

Stel dat we de **som** van deze getallen willen berekenen.

## met for

```
int sum = 0;
for(var n=0; n<numbers.Count; n++) {
    Console.WriteLine(numbers[n]);
    sum += numbers[n];
}
Console.WriteLine("Sum = " + sum);
```

## met ForEach

```
int sum = 0;
foreach(var n in numbers) {
    Console.WriteLine(n);
    sum += n;
}
Console.WriteLine("Sum = " + sum);
```


## met LINQ

```
int sum = numbers.Sum();
Console.WriteLine("Sum = " + sum);
```

Hiervoor is de `System.Linq`-namespace noodzakelijk. Zie ook [LINQ Introductie](LINQIntro.md).



## met de ForEach-method van een List

```
List<int> getallen = new List<int>() { 10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 1, 1 };

getallen.ForEach(x => Console.WriteLine(x)); // kan alleen met List, niet met IEnumerable
```

De `ForEach`-method neemt een `Action<T>` als parameter,
waarbij `T` afhankelijk is van het type van de `List`.
B.v. voor een `List<int>` : `Action<int>`.

De `Action`-template-parameter zegt hoeveel parameters we verwachten in de lambda expressie:
`(x) => Console.WriteLine(x)` is een lambda expressie met 1 `int` parameter.

> Hier (https://github.com/vbrh-immalle/SharpShell/blob/18561c3d105e1adbb3871e346fcde7a6f28f15be/Program.cs#L110)
> zie je een voorbeeld van een Action die **geen** parameters heeft : de methods die
> aangeroepen worden zijn parameterloos.


## Voorbeeld

https://dotnetfiddle.net/rtyIxI

