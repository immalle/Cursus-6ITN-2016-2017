# Constructors

## Overzicht

- Constructors zijn de methods die aangeroepn worden als we met `new` een
  nieuwe instantie maken van een object
- Er kunnen verschillende **overloads** zijn, d.w.z. verschillende constructors
  met verschillende parameters
- Als we geen constructor definiëren is er enkel de **default** constructor



## Default constructor

Default beschikt elk class over de *default constructor*
zonder parameters.

b.v. 

Deze class heeft verder nog helemaal niets:

```
public Varken {
}
```

toch kunnen we er al een object van maken, dankzij de
*default constructor zonder parameters* :

```
Varken piggie = new Varken();
```



## Constructors definiëren

Va. we 1 constructor toevoegen aan de class, wordt de default
constructor verwijderd.

b.v.

```
public Varken {

  private double gewicht;
  
  public Varken(double gewicht) {
    this.gewicht = gewicht;
  }
}
```

Meestal worden constructors gebruikt om het gemaakte object
te configureren.


