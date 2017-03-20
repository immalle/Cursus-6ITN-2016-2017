
Zolang je formulieren niet naar een server moet sturen,
heb je eigenlijk geen submit-knop nodig.

Eigenlijk heb je alleen maar formulier-elementen nodig.

We maken b.v. een textbox en voegen toe aan de body

	var inputbox = document.createElement("input");
	inputbox.type = "input";
	document.body.appendChild(inputbox);

Denk eraan dat veel formulier-elementen allemaal de tag `input`
gebruiken en dat het attribuut `type` bepaalt wat voor formulier-
element het is.

Maak een button:

	var button = document.createElement("input")
	button.type = "button"
	button.value = "Press me!";
	document.body.appendChild(button);

> Je zou ook een button kunnen maken met het `button`-element.

Voeg nu een event-handler toe aan het `click`-event v.d. button:

	button.addEventListener("click", function() { console.log('klik'); })

We moeten ook een manier hebben om de ingegeven waarde
uit de inputbox te halen.
Type daartoe iets in de inputbox en doe daarna:

	inputbox.value

Eventueel kan je ook een event listener koppelen, elke
keer als de inputbox wijzigt (`change`), als er op geklikt wordt
(`focus`), als er een toets ingedrukt wordt (`keypress`), ...

	inputbox.addEventListener("keypress", function(e) { console.log(e); })

Om nu dus iets te doen met de ingegeven waarde als op de knop geklikt wordt,
moet je `inputbox.value` gebruiken in de event handler van `button.onclick`.


