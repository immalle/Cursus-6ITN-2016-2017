# Algemeen

- Meestal single quotes (`'`) (soms double quotes `"`)
- Backticks om veldnamen *veilig* te benaderen
- standaard case INsensitive (hoofdletter ongevoelig)

# WHERE operators

filteren van queries

operators:

- `=`
- `!=` / `<>`
- `>`
- `<`
- `>=`
- `<=`
- `LIKE`
- `IS NULL` / `IS NOT NULL` (Opgelet: niet met `=`!)

# WHERE varia

- `BETWEEN 'A' and 'F'`
- `BETWEEN 2000 and 2010`
- `AND` : verfijnen van een query
- `OR` : uitbreiden van een query


# LIKE

wildcards:

- `_` : enkel karakter
- `%` : meerdere karakters
- `[abc]%` : begint met a, b of c (enkel SQL Server, voor MySQL gebruik REGEXP)
- `[^abc]%` of `[!abc]%` : begint NIET met a, b of c (idem)

> - In MySQL: `... WHERE naam REGEXP '^[abc]'`
> - Zie toekomstige les: regular expressions

# ORDER BY

sorteren van queries

- `ASC` : ascending / stijgend (default)
- `DESC` : descending / dalend

# LIMIT

- `LIMIT 3`

# Aggregatie-functies

```
SELECT COUNT(*) FROM fake_apps
```

# Voorbeelden (Codecademy)

- `SELECT DISTINCT genre FROM movies;`
- `SELECT * FROM movies WHERE imdb_rating > 8;`
- `SELECT * FROM movies WHERE name LIKE 'Se_en';`
- `SELECT * FROM movies WHERE name LIKE 'A%';`
- `SELECT * FROM movies WHERE name LIKE '%man%';`
- `SELECT * FROM movies WHERE name BETWEEN 'A' and 'J';`
- `SELECT * FROM movies WHERE year BETWEEN 1990 and 2000;`
- `SELECT * FROM movies WHERE year BETWEEN 1990 and 2000 AND genre = 'comedy';`
- `SELECT * FROM movies WHERE genre = 'comedy' OR year < 1980;`
- `SELECT * FROM movies ORDER BY imdb_rating DESC;`
- `SELECT * FROM movies ORDER BY imdb_rating ASC LIMIT 3;`




# Group by

```
SELECT price, COUNT(*) FROM fake_apps
GROUP BY price;
```

```
SELECT price, COUNT(*) FROM fake_apps
WHERE downloads > 20000
GROUP BY price;
```

# Sum

```
SELECT SUM(downloads) FROM fake_apps;
```

```
SELECT category, SUM(downloads) FROM fake_apps
GROUP BY category;
```

# Max

```
SELECT MAX(downloads) FROM fake_apps;
```

```
SELECT name, category, MAX(downloads) FROM fake_apps
GROUP BY category;
```

# Min

```
SELECT MIN(downloads) FROM fake_apps;
```

```
SELECT name, category, MIN(downloads) FROM fake_apps
GROUP BY category;
```

# Avg

```
SELECT AVG(downloads) FROM fake_apps;
```

```
SELECT price, AVG(downloads) FROM fake_apps
GROUP BY price;
```

```
SELECT price, ROUND(AVG(downloads), 2) FROM fake_apps
GROUP BY price;
```

Afronden naar `.0` :

```
SELECT price, ROUND(AVG(downloads)) FROM fake_apps
GROUP BY price;
```

# Joins

Soorten joins:

- cross-join
	- met `WHERE tabel1, tabel1`
	- redelijk zinloos
- inner-join
	- met `JOIN ... ON ...`
	- standaard join
- left-join
- right-join

# Tabellen joinen

Domweg aan elkaar plakken (cross-join),
er is geen echte betekenis aan deze query:

```
SELECT albums.name, albums.year, artists.name FROM albums, artists;
```

Wat wel zou kunnen (inner join):

```
SELECT albums.name, albums.year, artists.name FROM albums, artists WHERE albums.artist_id = artists.id;
```

Beter is om de `JOIN`/`ON`-syntax te gebruiken (inner join):

```
SELECT * FROM albums JOIN artists ON albums.artist_id = artists.id;
```

> Welke tabel je eerst zet, komt ook eerst.
> Volgorde van keys maakt niet uit.

> standaard: **inner join**

# Left join

Er zijn 2 albums die geen artist hebben.
Om deze ook te tonen:

```
SELECT * FROM albums LEFT JOIN artists ON albums.artist_id = artists.id;
```
