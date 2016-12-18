# Exceptions

Zie ook:

- https://www.dotnetperls.com/exception
- https://msdn.microsoft.com/en-us/library/ms173160.aspx

Voor een volledige lijst van Exceptions: https://msdn.microsoft.com/en-us/library/system.exception(v=vs.110).aspx

## Opvangen van exceptions

Doe je met een `try`-`catch`-blok.

## Werpen van exceptions

Een method kan `throw` gebruiken om een `Exception` te werpen.

De Exception wordt steeds verder doorgegeven aan de aanroepende method,
totdat een try/catch blok wordt gevonden. Is er geen try/catch-block in
de `Main`-method, zal het programma stoppen en wordt **default** de 
*stack trace* v.d. Exception getoond.

## Achtergrondinformatie

De class `Exception` is de moeder-class van alle Exceptions in C#.

Specifieke Exceptions kunnen meer informatie geven, b.v. `DivideByZeroException`.

Omdat er overerving gebruikt is, is er dus polymorfie aan het werk.
Een `DivideByZeroException` is dus ook een `Exception`.

## Eigen exceptions

Je kan zelf de class `Exception` ook overerven om nieuwe Exceptions te maken.
Of als je b.v. in je applicatie een Exception wil werpen die te maken heeft
met IO (input/output) kan je overerven van `System.IO.IOException`.

B.v. `System.IO.DirectoryNotFoundException` erft zelf over van `System.IO.Exception`.
Zie b.v. https://msdn.microsoft.com/en-us/library/system.io.directorynotfoundexception(v=vs.110).aspx

## Gebruik

Hou Exceptions voor echte exceptionele situaties.

Gewone foutafhandeling moet je niet altijd als een exception beschouwen.
Een exception is een *nette* manier om je programma te laten crashen omdat je nadien
toch niets zinvol meer zou kunnen doen.

