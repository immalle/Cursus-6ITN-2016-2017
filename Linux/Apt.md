# apt-get

## install

`apt-get` is een package manager die `.deb``-files download en installeert tesamen met eventuele dependencies (= andere `.deb`'s).

B.v. het downloaden en installeren van het `tree`-commando:

```
sudo apt-get install tree
```

## update

Op schijf wordt **lokaal** een lijst bijgehouden van beschikbare `.deb`-files.

De lijst van de gebruikte servers bevindt zich in `/etc/apt`.

Het updaten van de lijst met de laatste nieuwe packages kan met:

```
sudo apt-get update
```

# apt-cache

De lokale lijst met beschikbare packages kan men de *local package cache* (o.i.d.) noemen.

Zoeken of er een pakketje met `tree` in de naam aanwezig is, kan met:

```
apt-cache search tree
```

> Merk op dat je om te zoeken in de local package cache je geen `sudo`-rechten nodig hebt.

# dpkg

Achter de schermen wordt gebruik gemaakt van `dpkg`. Je kan die zelf ook gebruiken, b.v.

```
dpkg --install brackets.deb
```

> Dit kan nuttig zijn als je een `.deb`-file hebt gedownload van een website.

> `.deb`-packages worden gebruikt door Debian en afgeleiden zoals (X)Ubuntu.

# add-apt-repository

`add-apt-repository`` is een manier om nieuwe Internet-adressen toe te voegen aan de lijst van *Apt repositories*.

> Na het toevoegen eerst `sudo apt-get update` om de informatie over de nieuwe packages effectief te downloaden.

## PPA's

Naast de officiele (X)Ubuntu-Apt-repositories kan je ook PPA's toevoegen.
Die bevatten vaak **de laatste updates** maar zijn **potentieel onbetrouwbaar**.

B.v. `ppa:webupd8team/brackets` is een ppa (personal package archive).

Op https://launchpad.net/ubuntu/+ppas kan je zoeken naar PPA's.

b.v. https://launchpad.net/~webupd8team/+archive/ubuntu/brackets heeft als maintainer
https://launchpad.net/~nilarimogard.


# Ubuntu vs. andere distributies

## RPM

De tegenhanger `.deb`-files is in Fedora Core (of andere Red Hat afgeleide distributies) `.rpm` (RedHat Package Manager)).

De package manager heet er `yum`, waarmee je b.v. commando's kan geven als:

```
yum search tree
yum install tree
```

## TGZ

Soms worden in een `.tar.gz` (of gelijkaardig) bestand *binaries* gedistribueerd. Vaak wordt dan ook nog aangeduid voor welke processor en OS de binaries gebouwd zijn (`x84, `linux`, `darwin`, ...)

> Deze binaries kunnen dan manueel uitgepakt en ergens geplaatst worden, b.v. in `/usr/local`. Zie ook [Linux directory-structuur](Linux/Directories.md).

Een `.src.tar.gz` bevat de source-code.

## e.v.a.

PacMan, ...

