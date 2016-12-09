# Unicode in CSharp

```
char c = '\u21d0';
Console.WriteLine("Het unicode-karakter met code 21d0 = " + c);

int code = 0x21d0; // hex number
char unicodechar = Convert.ToChar(code);
//char unicodechar = (char)code; // alternatieve manier van converten

for(var i=0; i<10; i++) {
	unicodechar = (char)(code + i);
	Console.Write(unicodechar);
}

Console.WriteLine();
```

Belangrijk hierbij is dat je een font gebruikt dat deze
unicode-karakters kent. Op de Linux- en OSX-console werkt dit meestal,
op Windows niet altijd.

