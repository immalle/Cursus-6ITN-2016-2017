# Installatie

Zoek package:

```
apt-cache search apache php
```

Installeer:

```
sudo apt-get install libapache2-mod-php
```

> Apt-get script zal ook Apache-configuratie aanpassen!

# Test

Bewaar als `/var/www/html/phpinfo.php` :

```
<?php

phpinfo();

?>
```

> Hiermee wordt de php-functie `phpinfo()` uitgevoerd die een=
> HTML-pagina genereert met enorm veel informatie over Php en Apache!

En ga naar `http://localhost/phpinfo.php`.

# Denkoef.

- Wat gebeurt er met `.php`-bestanden als `libapache2-mod-php` **niet** geinstalleerd is?
  (Kijk met wireshark of naar de source via Firefox.)
- Wat is de **Apache Environment** ?
- Wat is de overeenkomst met `php -m` en de info verkregen via `phpinfo();`?
- Waarom werkt b.v. `echo $_SERVER['SERVER_NAME'];` in de interactieve shell niet
  maar wordt hij wel vermeld in `phpinfo()`?
- Merk op dat er geen **PDO-drivers** geinstalleerd zijn. Hoe zie je dat?
  (PDO = Php Data Objects, een API om met databases te communiceren)
