# XmlHttpRequest

Maak een nieuw `XMLHttpRequest`

	var xml = new XMLHttpRequest();

Kijk welke event handlers `XMLHttpRequest` ondersteund:

	xml.on (gebruik code completion)

Voeg een event listener toe voor als er data ontvangen wordt:

	xml.addEventListener("load", function(rsp) { console.log(rsp); });

> In een source-file zou je de vorige regel niet als one-liner schrijven
> maar over meerdere regels verdelen.

Open het `XMLHttpRequest`:

	xml.open("get", "http://thecatapi.com/api/images/get?format=src");

En verstuur het:

	xml.send();

Wanneer data ontvangen wordt, zal de event listener worden uitgevoerd,
in dit geval het afprinten op de console.


Breidt dit voorbeeld uit, zodat de event listener de verkregen data
(welke in dit geval een afbeelding is) afbeeldt op een pagina.


Probeer een event handler zoals:

	xml.addEventListener("load", function(rsp) { 
		var img = document.createElement("img");
		img.src = rsp.target.responseURL;
		document.body.appendChild(img);
	});


# Oef

Maak een html-bestand met daarin een knop en een `<ul>`. Een druk op de knop zal
een lijst van je repositories van GitHub opvragen en links ernaar toe toevoegen
aan de `<ul>`.

Als op de knop gedrukt wordt, zal dus een XMLHttpRequest verstuurd moeten worden.

Maak best een method om een link toe te voegen aan de `<ul>`. Uiteraard geef je de
`<ul>` best een `id`.

