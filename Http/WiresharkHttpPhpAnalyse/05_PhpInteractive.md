# Installatie

```
sudo apt-get install php
```

# php executable

Kan zowel door de webserver (apache) gebruikt worden als op de CLI.

- Toont info:

```
php -i
```

- Toont geinstalleerde modules (let op `session`):

```
php -m
```


# Interactive PHP shell

```
php -a
```

# Php code

Uit te proberen in interactive shell:

```
echo 3+4;
```

```
$a = 3;
echo $a;
echo $a + 2;
echo ++$a;
echo $a++;
echo $a;
var_dump($a);
```

```
for($i=0; $i<10; $i++) {
  echo $i;
}
```

superglobals (globale variabelen):

```
var_dump($_SERVER);
echo $_SERVER['HOME'];
```

# Extra: notities

Bewaar je `~/.php_history` file in je portfolio.

(Eventueel op te kuisen in een volgende commit.)
