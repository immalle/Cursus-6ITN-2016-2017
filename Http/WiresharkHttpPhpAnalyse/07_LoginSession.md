# Login-form

Bewaar als `/var/www/login.html` :

```
<form action="process_login.php" method="post">
<label for="username">Username: </label>
<input type="text" name="username"></input>
<br>
<label for="password">Password: </label>
<input type="password" name="password"></input>
<br>
<button type="submit" name="submit">Enter!</button>
</form>
```

> Oef: simuleer het submitten van dit form met `curl`.

> Oef: bekijk de loggings in `/var/www/apache2/access.log`.


# Login processing

Bewaar als `/var/www/process_login.php` :

```
<?php

echo "Username: ";
echo $_POST['username'];
echo "<br>";
echo "Password: ";
echo $_POST['password'];

?>
```

Bekijk de documentatie:

- http://php.net/manual/en/function.echo.php

Bekijk de request en responses met wireshark.

