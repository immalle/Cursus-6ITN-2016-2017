# Php services

Start lokale dev-server met `php -S localhost:8080`.

Gebruik de files `index.php`:

```
<?php

echo "GET";
var_dump($_GET);

echo "POST";
var_dump($_POST);

echo "SERVER";
var_dump($_SERVER);
```

en `session.php`:

```
<?php

session_start();

// $
```

en `header.php`:

```
<?php

header("Location: " . $_SERVER[HTTP_HOST] . "/index.php");
```

en `visit.php`:

```
<?php

session_start();

echo "SESSION" . PHP_EOL;
var_dump($_SESSION);

echo "SERVER" . PHP_EOL;
var_dump($_SERVER);

$visitorsfile = fopen("visitors.txt", "a");

$str = "[" . date("Y-m-d H:i:s") . "] Visit from " . $_SERVER['REMOTE_ADDR'] . " with " . $_SERVER['HTTP_USER_AGENT'] . "." . PHP_EOL;

fwrite($visitorsfile, $str);
fclose($visitorsfile);
```

`json.php`:

```
<?php

header('Content-Type: application/json');

/*
// enkel inhoud van $_SERVER
$rsp = json_encode($_SERVER);
echo $rsp;
*/

// inhoud van meerdere interessante PHP-superglobals

// eerst maken we een python array met 3 keys
$rsp = [
  'server' => $_SERVER,
  'get' => $_GET,
  'post' => $_POST,
  'imma' => [
    'klas' =>` '6ITN',
    'schooljaar' => '2016-2017'
  ]
];

echo json_encode($rsp);
```


en eventueel `info.php`:

```
<?php

phpinfo();
```


## Requests

Doe vervolgens enkele requests:

```
$index = invoke-webrequest http://localhost:8080 
$index
$index.Headers
$header = invoke-webrequest http://localhost:8080/header.php
$header = invoke-webrequest http://localhost:8080/header.php -ErrorAction Ignore
$header = invoke-webrequest http://localhost:8080/header.php -ErrorAction Ignore -MaximumRedirection 0
$header
$header.Headers
(invoke-webrequest http://localhost:8080/visit.php).Headers
(invoke-webrequest http://localhost:8080/visit.php).Headers // check PHPSESSID
(invoke-webrequest http://localhost:8080/visit.php).Headers // check PHPSESSID
```

Om het cookie dat je krijgt van de server op te slaan:

```
$cookie = (invoke-webrequest http://localhost:8080/visit.php).Headers['Set-Cookie']
$cookie
```

Gebruik nu dit cookie in enkele requests: zie https://gripdev.wordpress.com/2015/05/27/powershell-invoke-webrequest-with-a-cookie/

Zie ook https://github.com/vbrh-immalle/phpcookieclicker

Een makkelijkere manier is om de `-SessionVariabele`-parameter te gebruiken.

```
$visit = invoke-webrequest http://localhost:8080/visit.php -SessionVariable sess
$sess
```

Van welk type is `$sess`?


## Json 

```
$json = Invoke-WebRequest http://localhost:8080/json.php -Method Post -Body "naam=willy"
$json
$json.content
$json | gm # bekijk het type van $json
$jsondata = ($json.content | ConvertFrom-Json)
$jsondata | gm
$jsondata
$jsondata.server
$jsondata.server.HTTP_HOST
$jsondata.imma
$jsondata.imma.klas
```

Maar we kunnen ook `Invoke-RestMethod` gebruiken. Die converteert zelf de json-data naar
powershell objecten.

```
$json = invoke-restmethod http://localhost:8080/json.php?name=hallo
$json
$json | format-list
$json | gm # bekijk het type van $json
$jsondata
$jsondata.server
$jsondata.server.HTTP_HOST
$jsondata.imma
$jsondata.imma.klas
```

> Typisch aan REST is dat er geen **STATE** wordt bijgehouden en we dus ook niet met
> session-variabelen gaan werken. (REST = Representational State Transfer)

