# Powershell ISE

Maak een nieuw `Regex`-object (vanuit DotNet libraries):

```
$re = new-object Regex("[a-z]{2,4}")
```

En test enkele strings. Welke matches krijg je terug?

```
$re.Match("a");
$re.Match("aa");
$re.Match("aaa");
$re.Match("aaaa");
$re.Match("aaaaa");
$re.Match("aaaaaa");
```

Het antwoord ziet er standaard zo uit:

```
Groups   : {aaaa}
Success  : True
Captures : {aaaa}
Index    : 0
Length   : 4
Value    : aaaa
```

Maak een nieuwe Regex maar gebruik de begin- en eindmarkerking `^` en `$`:

```
$re = new-object Regex("^[a-z]{2,4}$")
$re.Match("a")
$re.Match("aa")
$re.Match("aaa")
$re.Match("aaaa")
$re.Match("aaaaaa")
```

