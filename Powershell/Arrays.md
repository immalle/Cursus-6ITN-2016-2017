# Arrays

```
$numbers = 1, 2, 3, 4, 5, 6
$words = "one", "two", "three", "four", "five", "six"
```

# Associative arrays

Associatieve arrays zijn zowel dictionaries als objecten.
De keys fungeren als *properties*.

Een custom object met 2 properties:

```
$headers = @{"Content-Type"="application/json"; "X-MyHeaderParam" = 3}
```

> Let op: `;` als scheidingsteken!

## Experimenten

- Moeten de keys `"` hebben als er geen `-` in voorkomt?
- Kunnen we een array gebruiken als value?

```
$pizza = @{Crust="Thin";Toppings="artichoke", "blue olive", "cheese"}
$pizza
$pizza | gm
$pizza.Toppings
$pizza.Toppings.GetType()
$pizza.Toppings | gm
```

## Conclusies

- Met `@{...}` gemaakte arrays zijn gelijkaardig aan objecten maar van 
het .Net type `System.Collection.Hashtable`.
- Met `GetType()` krijgen we altijd het echte type te zien.
- Met `| Get-Member` (of `| gm`) zien we bij een array het type v.d.
  elementen, niet het type v.d. array zelf.
- De keys van een associatieve array (dictionary) moeten niet tussen
  quotes (`"`) staan als er geen speciale karakters in voorkomen.
