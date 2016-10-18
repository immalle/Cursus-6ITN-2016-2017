# LINQ

- LINQ = Language Integrated Query
- Vanaf C# 3.0 
- Geïmplementeerd dankzij *Extension methods* (Zie [Extension methods](CSharp/ExtensionMethods.md))

# 2 soorten syntax

- query syntax (vgl. met SQL)
- fluent syntax (gebruikt lambda-functies), te beschouwen als een *transportband*

http://stackoverflow.com/questions/214500/linq-fluent-and-query-expression-is-there-any-benefits-of-one-over-other

## Wanneer wat gebruiken?

Je mag kiezen!

Intern wordt *query syntax* altijd eerst omgezet naar *fluent syntax*.

Je kan meer doen met *fluent syntax* maar *query syntax* is soms makkelijker te lezen.

Dit zijn de enige *operators* die *query syntax* ondersteund:

- `Where(...)`
- `Select(...)`
- `SelectMany(...)`
- `OrderBy(...)`
- `ThenBy(...)`
- `OrderByDescending(...)`
- `ThenByDescending(...)`
- `GroupBy(...)`
- `Join(...)`
- `GroupJoin(...)`

Enkele extension methods die enkel met *fluent syntax* werken:

- `Reverse()` geeft een collectie in omgekeerde volgorde
- `Take(3)` geeft de eerste 3 elementen v.e. collectie
- `First()` geeft het eerste element v.e. collectie
- `Last()` geeft het laatste element v.e. collectie
- `Skip(2)` geeft een collectie zonder de eerste 2 elementen
- `Min()` geeft het kleinste element v.e. collectie
- `Max()` geeft het hoogste element v.e. collectie
- `Concat(...)` plakt 2 collecties aan elkaar
- `Union(...)` plakt 2 collecties aan elkaar zonder dubbele elementen

Gelukkig mag je de 2 ook door elkaar gebruiken!

Je kan ook C#-code schrijven waarbij het niet onmiddellijk duidelijk is 
dat je LINQ gebruikt, b.v.:

```
var getallen = new List<int>() { 1, 2, 3, 4, 5, 6, 7, 8, 9 };

Console.WriteLine("Grootste getal: " + getallen.Max());
Console.WriteLine("Kleinste getal: " + getallen.Min());
```

# IEnumerable / IQueryable

Voor het gemak, kan je een query steeds definieren met

```
var qry = ...
```

maar weet dat het type eigenlijk `IEnumerable` of `IQueryable` is.

Bijgevolg kan je over de query-resultaten itereren met b.v. `foreach`:

```
foreach(var q in qry)
{
	Console.WriteLine(q....);
}
```

> `IEnumerable` wordt gebruikt bij *LINQ to objects* : de query
wordt in de code zelf uitgevoerd.

> `IQueryable` erft over van `IEnumerable` en wordt o.a. gebruikt
bij *LINQ to SQL* en *LINQ to Entities*, m.a.w. bij databases.
Het zorgt er voor dat de query omgezet wordt naar SQL en **door de
database wordt uitgevoerd** en niet in het C# programma zelf.
(Dit kan het verschil betekenen tussen een tabel met 1000 records
of met 10 records v.d. database verkrijgen.)

# Namespace

Vergeet niet om de LINQ-namespace te includen:

```
using System.Linq....;
```

Linq werkt dankzij *extensions methods*. D.w.z. dat er methods gedefinieerd worden
die op een object kunnen gebruikt worden alsof ze in de class zelf 
geimplementeerd werden.

Deze *extensions methods* zijn dus in `System.Linq.*` geïmplementeerd.

(Je kan ook zelf extensions methods schrijven, zie 
http://lmgtfy.com/?q=extension+methods )

# van traditioneel over query naar fluent

http://jesseliberty.com/2011/01/27/linq-and-fluent-programming/


