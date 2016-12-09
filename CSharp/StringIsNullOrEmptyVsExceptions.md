# Exceptions en String.IsNullOrEmpty

Exceptions moet je proberen zoveel mogelijk te vermijden.
Hou ze echt voor uitzonderlijke situaties.

Dus liever:

```
if (String.IsNullOrEmpty(s)) 
        return "is null or empty";
else
        return String.Format("(\"{0}\") is neither null nor empty", s);
}
```

dan

```
String s = null;

Console.WriteLine("The value of the string is '{0}'", s);

try {
 Console.WriteLine("String length is {0}", s.Length);
}
catch (NullReferenceException e) {
 Console.WriteLine(e.Message);
}
```

