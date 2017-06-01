
Door de asynchrone aard van Javascript in de browser,
moeten we heel veel met **events** en **event handlers** werken.

> Event handlers worden soms ook wel **callback**'s genoemd.

B.v. een knop heeft een `click`-event, dat we kunnen afhandelen:

	var button = document.createElement("button");
	document.body.appendChild(button);
	button.innerHTML = "Klik op mij!";

	button.addEventListener("click", function() { console.log("klik"); });

Sommige events sturen extra data door, zoals het `keypress`-event.
Dit moeten we afhandelen met een **parameter** in de event handler:

We maken een textarea:

	var textarea = document.createElement("textarea");
	document.body.appendChild(textarea);
	textarea.cols = 80;
	textarea.rows = 10;

En we koppelen het `keypress`-event met een event handler
(hier op de oude manier, met `on...`):

	textarea.onkeypress = function(key) { 
		console.log(key);
	}

Of op de nieuwe manier:

	textarea.addEventListener("keypress", function(key) { 
		console.log(key); 
	});


Elke keer als nu op een toets gedrukt wordt,
wordt het `key`-object afgebeeld op de console.

**Nu is het de opdracht om het `key`-object te bestuderen 
om de interessante properties te weten te komen.**
Je kan ook documentatie opzoeken eens je weet wat voor
object het is.

We zien b.v. dat dit object van het type `KeyboardEvent` is (in Chrome),
dat we b.v. met de `.shiftKey` property kunnen kijken of shift ingedrukt was
en dat we de keycode met de `.which`-property te weten komen.

We kunnen deze code trouwens met `String.fromCharCode` omzetten naar een string :

	textarea.addEventListener("keypress", function(key) { 
		console.log(String.fromCharCode(key.which)); 
	});

> Merk dus op dat je een website ook keyboard-controlled kunt maken,
> zolang je maar geen toets-combinaties gebruikt die al door Chrome of het OS
> gebruikt worden (zoals CTRL-W, CTRL-S, ...).



Iets gelijkaardig kunnen we doen voor het response van een `XMLHttpRequest`!

> Net zoals DateTime's zijn key-presses in Javascript niet super gebruikersvriendelijk.
> Gebruik daarom externe libraries zoals Mousetrap (https://craig.is/killing/mice) of
> https://momentjs.com/
