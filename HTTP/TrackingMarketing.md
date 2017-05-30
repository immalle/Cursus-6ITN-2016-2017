# Tracking for digital marketing

---

## De bedoeling van marketeers (en business-owners)

- ``conversies'' meten (aankoop, inschrijving op nieuwsbrief, aanmaken van een account, ...)
- attribueren (wat zorgde voor de conversie? hoe lang duurde het? was het paid search, ads, organic search?)

Bijgevolg:

- gebruikers tracken op zoveel mogelijk (verschillende) websites
- Ad servers (Doubleclick, Google, Facebook, ...) gebruiken een `user_id` over verschillende server-domeinen heen

---

## Technologie

In elk response van een webserver zit een **domein-gebonden** cookie.

Hoe kunnen we users tracken over verschillende domeinen heen?

- (third-party) cookies
- HTTP redirect
    - een link gaat eigenlijk eerst naar de servers van een marketingbureau maar zeer snel gebeurt een redirect naar de eigenlijk pagina
    - b.v. aanklikken van e-mail nieuwsbrief met code in URL
    - b.v. aanklikken van facebook-post
- single transparant pixel
    - `img`-tag die wordt gedownload v.e. andere server
- javascript
    - mogelijkheid tot opslaan van *referring URL* en 
  
- zie ook https://en.wikipedia.org/wiki/Web_beacon


Uiteindelijk wordt al deze data (IP, UserAgent, reffering url, user_id's, ...) in log-files of speciale databases bewaard zodat het later kan doorzocht worden.

---

## Experimenten

- Bekijk de mail headers van reclame-berichten of terugkerende nieuwsbrieven die je krijgt
    - Welke online mail-service wordt gebruikt? (b.v. mailgun, mailchimp, ...)
    - Zijn er cryptografische handtekeningen te vinden? Waarom? (zie ook https://tools.ietf.org/html/draft-andersen-arc-00, https://blog.returnpath.com/how-to-explain-authenticated-received-chain-arc-in-plain-english-2/ of http://hashcash.org/)
    - is er HTML-content? Waar gaan de links naartoe? Maken deze verbinding met een server? Wat en wanneer wordt hiermee gemeten?

- Ga naar een website met veel reclame (b.v. http://hln.be) en zoek alle elementen die je tracken
    - Bekijk de browser-console
    - Bekijk de cookies op dit domein

- Vind je (m.b.v. Chrome) gemeenschappelijke cookies op http://hln.be en http://tweakers.be?
    - Bekijk de headers en cookies met `Invoke-WebRequest`
        - Wat zie je als je zelf geen cookies meestuurt?
        - Wat zie je als je eerder ontvangen cookies meestuurt?

- Geef voorbeelden van websites die uitleggen hoe je hun marketing- of analyse-systeem kan toevoegen aan je eigen site, b.v. Google Analytics, Facebook Connect, Gemius, ...

- Slightly related: 
    - de klantenkaart in het warenhuis
    - wist je dat Colruyt tegenwoordig ook Free WiFi aanbiedt in haar winkels? Wat zijn de mogelijkheden (voor Colruyt)?


