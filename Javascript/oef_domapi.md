
> Voer alle commando's uit in de **javascript console** van een browser.
> Ga eerst naar een gepaste webpagina (b.v. `about:blank` of een bestaand `.html`-bestand met een minimum aan html-elementen.
> (Voor de commando's eindigend op `.constructor` is Chrome nodig voor zinnige output.)
> (NodeJS heeft geen DOM API!)


# Het maken van elementen

Er zijn DOM API functies om elementen te maken
maar het is vaak gemakkelijker om `.innerHTML` te gebruiken.

Maak een element.

	var div = document.createElement("div")

Toon de naam van deze node (knoop):

	div.nodeName

Wat is het type van `div.nodeName`?

	div.nodeName.constructor

Welke kind nodes heeft dit element?

	div.childNodes

Heeft dit element al een parent?

	div.parentNode

Wijzig de `.innerHTML` :

	div.innerHTML = "<p>Hello</p>"

Zijn er nu kind-nodes?

	div.childNodes

Wijzig `.innerHTML` opnieuw:

	div.innerHTML = "<p>Hello</p><ul><li>item 1</li><li>item 2</li></ul>"

Hoeveel kind-nodes zullen er nu zijn?

	div.childNodes	

Hoe kan je alle kind-nodes van de `ul` te pakken krijgen?

	div.childNodes[1].childNodes

Geef `div` een parent element (en maak het ineens zichtbaar).

	document.body.appendChild(div)


# Extra


Er bestaat ook `.parentElement`. Is dit hetzelfde als `.parentNode`?

	div.parentElement
	div.parentNode
	div.parentNode == div.parentElement
	div.parentNode === div.parentElement
	div.parentNode.constructor
	div.parentElement.constructor

Er bestaat ook `.children`. Is dit hetzelfde als `.childNodes`?

	div.children
	div.childNodes
	div.children == div.childNodes
	div.children.constructor
	div.childNodes.constructor


# Verschil tussen text en html

Wat is het verschil tussen `.innerText` en `.innerHTML`.

Probeer uit door

	div.innerText = "<h2>hallo</h2>";
	div.innerHTML = "<h2>hallo</h2>";

Probeer ook eens

	escape("<h2>hallo</h2>")

of (aangezien `escape` deprecated is)

	encodeURI("<h2>hallo</h2>");
        encodeURIComponent("<h2>hallo</h2>");

Merk: dit wordt gebruikt voor het encoden van speciale karakters in een URL.

Voor het escapen van HTML naar ampersand-codes, kunnen deze functies gebruikt worden:
(bron: http://shebang.brandonmintern.com/foolproof-html-escaping-in-javascript/)

	function escapeHtml(str) {
	    var div = document.createElement('div');
	    div.appendChild(document.createTextNode(str));
	    return div.innerHTML;
	};

	// UNSAFE with unsafe strings; only use on previously-escaped ones!
	function unescapeHtml(escapedStr) {
	    var div = document.createElement('div');
	    div.innerHTML = escapedStr;
	    var child = div.childNodes[0];
	    return child ? child.nodeValue : '';
	};

