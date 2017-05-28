

Maak een leeg object

	var p = {}

Voeg 2 properties toe

	p.naam = "Jos"
	p.leeftijd = 56;

Je kan ze ook zo maken

	p['naam'] = "Jos";
	p['leeftijd'] = 56;

En je kan ze zo tonen:

	p.naam
	console.log(p.naam)

Of als inhoud van een element zetten:

	var div = document.getElementById("divje");
	div.innerHTML = p.naam;

In werkelijkheid zou je voor het object af te beelden, b.v. deze html-snippet gebruiken

	<div id="persoon">
		<div id="naam"></div>
		<div id="leeftijd"></div>
	</div>

Als we javascript-object naar een server willen sturen,
zullen we het object eerst omzetten naar een string:

	JSON.stringify(p);

Als we van een server een string terugkrijgen in JSON-formaat,
kunnen we dit gemakkelijk omzetten naar een javascript-object:

	var p = JSON.parse('{"naam":"Jef", "leeftijd": 49}');

> `JSON.parse` werkt niet als single quotes `'` worden gebruikt:

> 	JSON.parse("{'naam':'Jef', 'leeftijd': 49}");


Nu kunnen de properties van dit object ook weer geraadpleegd worden:

	p.naam
	p.leeftijd



