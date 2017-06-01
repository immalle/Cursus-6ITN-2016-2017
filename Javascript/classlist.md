# Classlist

Een erg handig truukje is om een CSS-class te maken om iets accentueren (b.v.
een gemarkeerd item in een todo-lijst) door het togglen van een class.

Maak b.v. een class:

``` 
.marked {
  background-color: yellow;
}
```

Als je nu bepaalde elementen wil markeren, kan dat het gemakkelijkst met de `classList`-property:

```
var elem = document.getElementById("tomark");

elem.classList.toggle('marked');
```

Probeer het zelf door aan alle paragrafen (b.v.
van [deze html file](scrolltop.html)) een click-event-handler toe te voegen die
dit kan togglen.

Kijk ook eens naar de andere methods van `classList`:

- https://www.w3schools.com/jsref/prop_element_classlist.asp
- https://developer.mozilla.org/en-US/docs/Web/API/Element/classList

