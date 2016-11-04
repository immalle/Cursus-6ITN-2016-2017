# Curl

Curl is een command line tool om verbinding te maken met allerlei services. 
Het wordt vaak gebruikt om webservices te testen of om een bestand te downloaden. 

Zie ook `wget`.

Kijk op <http://chocolatey.org/packages/curl> wat `curl` allemaal ondersteund.

Oef: Zoek op wat elke service is, geef een korte beschrijving en 
zeg op welke TCP-poortnummer deze services standaard draaien.

- DICT (<https://en.wikipedia.org/wiki/DICT>)
- FTP
- IMAP
- LDAP
- POP3
- SMTP
- SCP
- HTTP
- HTTP POST
- HTTP PUT
- HTTP form based upload
- cookies
- ...

## gebruik

Download de hele pagina (en toon op `stdout`):

	curl "http://www.google.be"

Controleer de SSL certificaten niet (zodat `https` ook werkt):

	curl -k "https://www.google.be"
	curl --insecure "https://www.google.be"

Toon enkel de HTTP-header:

	curl -k -I "https://www.google.be"
	curl -k --head "https://www.google.be"


## verbose

Toon meer info over wat precies wordt verzonden:

	curl "http://www.google.be" --verbose
	curl "http://www.google.be" -v

Eventueel kan zelf nog meer getoond worden met `--trace` en `--trace-ascii`.
Dit kan alleen naar een aparte file gelogd worden.


## POST-method

http://superuser.com/questions/149329/what-is-the-curl-command-line-syntax-to-do-a-post-request

http://stackoverflow.com/questions/14551194/how-are-parameters-sent-in-an-http-post-request

### Content-type

standaard: `application/x-www-form-urlencoded`

http://stackoverflow.com/questions/9870523/differences-in-application-json-and-application-x-www-form-urlencoded

liever b.v.: `request.ContentType = "application/json; charset=utf-8"`

