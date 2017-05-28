# Logs

Bekijk `/var/log/apache2/access.log`.

Een log-regel ziet er zo uit:

```
127.0.0.1 - - [02/Nov/2016:16:33:58 +0100] "GET /login.html HTTP/1.1" 200 512 "-" "Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:48.0) Gecko/20100101 Firefox/48.0"
```

De velden zijn :

- IP-adres van het request
- leeg
- datum + uur + tijdzone
- request + parameters (b.v. GET /login.html)
- 200 : response code
- 512 : ?
- "-" : ?
- "Mozilla/5.0 ..." : client programma


# Wget

Gebruik het CLI-tooltje `wget` om vanaf de CLI een request naar Apache te sturen en bekijk de logging.

Logging:

```
127.0.0.1 - - [04/Nov/2016:21:54:16 +0100] "GET /login.html HTTP/1.1" 200 600 "-" "Wget/1.17.1 (linux-gnu)"
```


# Curl

Gebruik het CLI-tooltje `curl` (installeer indien nodig) om vanaf de CLI een request naar Apache te sturen en bekijk de logging.

Logging:

```
127.0.0.1 - - [04/Nov/2016:22:08:00 +0100] "GET /login.html HTTP/1.1" 200 544 "-" "curl/7.47.0"
```
