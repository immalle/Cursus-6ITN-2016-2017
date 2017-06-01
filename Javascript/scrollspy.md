# ScrollSpy

Er bestaan scrollspy-libraries. Kijk b.v. naar die van bootstrap:

http://getbootstrap.com/javascript/#scrollspy

Maar op basis van welke javascript- en DOM-functionaliteit werkt dit eigenlijk?

## Scroll-properties en -methods

O.a. met `document.body.scrollTop` kan de huidige stand van de scrollbar worden vastgesteld.

Er bestaat ook een handige functie om een bepaald HTML-element zeker zichtbaar te maken:
https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView

Uiteraard moet je eerst het element te pakken krijgen met `getElementById`,
`querySelector` of eventueel met jQuery.

## Oef.

Probeer zelf de scroll-properties uit op de console met [deze HTML-file](scrolltop.html).

