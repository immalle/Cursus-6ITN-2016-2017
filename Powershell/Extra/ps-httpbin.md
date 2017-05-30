
## HTTP Status

```
invoke-webrequest http://httpbin.org/status/101
```

Of meerdere tegelijk:

```
101, 102, 103, 104, 105 | %{ invoke-webrequest http://httpbin.org/status/$_ }
```

TIP: bekijk `alias %`


## GET en POST

```
invoke-webrequest -Method Post httpbin.org/post -body "key=value&key2=value2"
```

Probeer zelf GET, PUT, PATCH, ...


## Basic Authentication

Basic Authentication gebeurt normaal gezien via een pop-up venster van de browser.

Welke foutmelding krijg je? Is dat veilig?

```
invoke-webrequest httpbin.org/basic-auth/willy/wally 
```
Bovendien worden username en wachtwoord slechts `Base64`-encoded.
Dit is dus niet veilig over HTTP, eventueel wel over HTTPS.


Wat is het voordeel van deze implementatie van basic authentication?

```
invoke-webrequest http://httpbin.org/hidden-basic-auth/willy/wally
```


```
(invoke-restmethod httpbin.org/basic-auth/willy/wally -Credential (Get-Credential)).headers
```



## Content-Type
   
```
(invoke-restmethod httpbin.org/post -method post -ContentType application/json).headers."content-type"
```

## Redirection

```
invoke-webrequest httpbin.org/redirect/10 -MaximumRedirection 10
invoke-webrequest httpbin.org/redirect/10 -MaximumRedirection 9
```

