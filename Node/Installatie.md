# Installatie

## Download

We willen liefst de laatste versie van node. Daarom zullen we niet de standaard
packages van (X)Ubuntu (of de meeste andere Linux-distributies) gebruiken.

Het is mogelijk om een extra *apt-repository-source* toe te voegen (dat gebeurt
in de configuratie-bestanden van `apt` in `/etc/apt/sources.list` door het
script `apt-add-repository`). (X)Ubuntu zal dan de executables `npm` (de node
package manager) en `node` (node zelf) in `/usr/bin/` of `/usr/local/bin`
zetten.

Maar waarom niet gewoon de laatste versie van node rechtstreeks van de website
halen. Deze manier van werken is niet zo moeilijk als je zou verwachten en biedt
veel meer duidelijkheid bij een eventuele uninstall of upgrade of zelfs om
verschillende versies door elkaar heen te gebruiken.

Download daarom de Linux-binaries voor je 32- of 64-bit systeem.

B.v. `node-v6.9.1-linux-x64.tar.xz`

We zullen node installeren in de eigen home-directory `~` (of `/home/username`)
zodat we zeker geen root-rechten nodig hebben, ook niet als we later met `npm`
extra packages installeren.

- `tar xf node-v6.9.1-linux-x64.tar.xz`
- er is nu een map (`node-v6.9.1`) gemaakt
- bekijk de inhoud van deze map en de submap `bin`, hierin staan de executables
- deze executables moeten aan het **PATH** toegevoegd worden


Omdat het lastig is om een specifiek versie-nummer te gebruiken, maken we een
symbolische link aan van `node` naar de specifieke directory:

- `ln -s node-v.6.9.1 node`

Nu kunnen we in `.zshrc` (of `.bashrc` als je bash gebruikt) de
PATH-omgevingsvariabele updaten:

- `export PATH=$PATH:~/node/bin`

Importeer de instellingen in de shell:

- `. ~/.zshrc`

Controleer of `node` en `npm` werken met

- `node --version`
- `npm --version`

