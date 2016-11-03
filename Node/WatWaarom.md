# Wat is node en waarom willen we het gebruiken?

Bij de installatie van node krijg je 2 executables ter beschikking in de shell:

- `node` : node zelf waarme javascript-code kan uitgevoerd worden
- `npm` : de node package manager

## Javascript

Node maakt gebruik van de (grotendeels) in C++ (met een beetje Python)
geschreven **V8 javascript engine** die ook Chrome gebruikt. Het *selling-point*
van Node was (en is) dat javascript als programmeertaal kan gebruikt worden aan
de server-kant, als back-end voor (database-gestuurde) web-applicaties. Er zijn
enkele redenen waarom dit interessant is:

- hoewel een node-programma in 1 thread draait, is het toch performant om
  verschillende gelijktijdige client-connecties af te handelen omdat in
  javascript code typisch **asynchroon** / **non-blocking** wordt uitgevoerd
  (later meer hierover)
- javascript wordt gebruikt aan de back-end **EN** aan de front-end :
  *full-stack javascript*
- front-end developers die javascript al kennen, kunnen hiermee ook werken aan
  de back-end

## Hoe zullen wij het gebruiken?

Wij zullen node niet gebruiken als server-platform maar enkel als
**ondersteuning van front-end developemnt**, meerbepaald:

- development tool (waarbij dan toch een mini-server komt kijken, waarvoor node
  ideaal is)
- packaging tool (bundler) van CSS en javascript-libraries

### Als development-tool

- automatische refresh van gesavede HTML-, CSS- en javascript-bestanden (zoals
  b.v. ook standaard aanwezig in Brackets, Visual Studio, ...)

### Als packaging-tool

Dankzij een **build**-stap kunnen we een website optimaliseren en gebruik maken
van extra libraries:

- SCSS of SASS wat geconverteerd wordt naar CSS
- Verschillende javascript-bestanden die gebundelt worden tot 1
  javascript-bestand met b.v. `browserify`

Met `npm` kunnen talloze (kleine) libraries geinstalleerd worden die het
programmeerwerk makkelijker maken en meer mogelijkheden bieden dan mogelijk zou
zijn met CDN-links.

