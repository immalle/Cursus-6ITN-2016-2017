
# Situering

HTTP is een Applicatie-protocol, momenteel bovenop TCP/IP.

- https://nl.wikipedia.org/wiki/Hypertext_Transfer_Protocol
- het is tekst-gebaseerd
- het heeft een *header* met *key-value*-velden
- de header eindigt met 2 *enters* `\r\n\r\n` en meestal een `Content-length`-veld
- het heeft een *body* (met een lengte `Content-length`
- er zijn:
	- requests
	- responses

![TCP-IP stack](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c4/IP_stack_connections.svg/490px-IP_stack_connections.svg.png)

# Praktische experimenten

- `ping` gebruikt het `ICMP`-protocol
- `tracert` (`traceroute`) toont alle routers onderweg naar een host
- zie ook *lagenmodel* : https://nl.wikipedia.org/wiki/TCP/IP
