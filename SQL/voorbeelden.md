# Data

Albums :

```
id;name;artist_id;year
1;A Hard Days Night;1;1964
2;Elvis Presley;2;1956
3;1989;;2014
4;Yellow Submarine;1;1968
5;Hey Jude;1;1970
6;Like a Virgin;4;1984
7;From Elvis in Memphis;2;1969
8;Bad;3;1987
9;Elton John;5;1970
10;Like a Prayer;4;1989
11;The Dark Side of the Moon;7;1973
12;Thriller;3;1982
13;Unorthodox Jukebox;;2012
14;The Wall;7;1979
```

Artists:

```
id;name
1;The Beatles
2;Elvis Presley
3;Michael Jackson
4;Madonna
5;Elton John
6;Led Zeppelin
7;Pink Floyd
```


# Left Join vs. Inner Join

Wat gebeurt er als je `LEFT JOIN` vervangt door `INNER JOIN`?

> Er zijn 2 albums waar geen artiest voor ingevuld is. 
> Ze worden met `LEFT JOIN` toch geselecteerd.

```
SELECT COUNT(*) 
FROM Albums
LEFT JOIN Artists
ON Albums.artist_id = Artists.id;
```

Er zijn andere, zoals `RIGHT JOIN`, ...


## Group By en aggregatie-functies

> Kan enkel gebruikt worden bij aggregatie-functies, zoals :
> - `COUNT`
> - `SUM`
> - `MAX`
> - `MIN`
> - `AVG`

`GROUP BY` signaleert dat de gebruikte aggregatie-functie (b.v. `COUNT`)
moet uitgevoerd worden voor alle *distincte* `Year`'s.

```
SELECT Year, COUNT(*) 
FROM Albums
GROUP BY Year;
```
> Zonder `GROUP BY` wordt `COUNT` uitgevoerd voor **alle** records.

## Having

Extra filters op de groeperingen :

```
SELECT Year, COUNT(*) 
FROM Albums
GROUP BY Year
HAVING Year > 1990;
```

## Simpele berekeningen

```
SELECT 25/5;
```
