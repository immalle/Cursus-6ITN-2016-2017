
# SimpleHTTPServer

Met Python is het heel gemakkelijk om de huidige directory te serven:

Voor python 2.x:

	python -m SimpleHTTPServer

of om op poort 8080 te serven:

	python -m SimpleHTTPServer 8080

Voor python 3.x:

	python -m http.server

Surf nu naar b.v. http://localhost:8080 en je zou alle bestanden uit
deze directory moeten zien.

> Merk op dat dit voor de webbrowser anders is, dan dat je een html-file
> gewoon rechtstreeks opent. Nu is er immers een HTTP-verbinding gebruikt
> om het HTML-bestand door te sturen. Bijgevolg kan je b.v. met cookies
> werken wat met een gewone file niet mogelijk is.
