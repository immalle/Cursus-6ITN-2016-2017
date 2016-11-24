# Override

**Overriden** (overschrijven) doe je met methods die in een
bovenliggende class als **virtual** of **abstract** gedefinieerd zijn.


## Object

Elke class in C# erft over van `Object` en deze heeft 1 interessante
`virtual` method: `ToString()`.

Als je eigen class nood heeft aan een ToString-conversie, is het dus
best deze method te **overriden**:

```
abstract class Dier
{
    public virtual double Gewicht { get; set; }

    public abstract void MaakGeluid();
    
    public override string ToString()
    {
        return String.Format("Het dier weegt {0} kg.", this.Gewicht);
    }
} 
```

## Voorbeeld

https://dotnetfiddle.net/DcA3k4
