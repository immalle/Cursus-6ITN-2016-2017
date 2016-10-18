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
    Console.WriteLine(n);
    sum += n;
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


## Voorbeeld

https://dotnetfiddle.net/rtyIxI

