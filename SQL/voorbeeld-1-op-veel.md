
![annoncernon ER](img/annoncernon.png)

```
create schema voorbeeld_1_op_veel;
use voorbeeld_1_op_veel;

create table UserAccount(
    id int not null auto_increment primary key,
    name text not null,
    email text
);

create table Annonce(
    id int not null auto_increment primary key,
    user_id int not null,
    tijdstip datetime,
    omschrijving text,
    prijs double
);

insert into UserAccount(id, name, email)
values 
(1, "Joske", "joske@immalle.be"),
(2, "Jefke", "jefke@immalle.be");

insert into Annonce(id, user_id, tijdstip, omschrijving, prijs)
values
(1, 1, "2016-04-18 08:00:00", "Een zo goed als nieuwe laptop!", 199.95),
(2, 1, "2016-04-18 08:30:00", "Een zo goed als nieuwe GSM!", 179.50),
(3, 2, "2016-04-18 08:30:00", "Gratis puppies!", 0);


/* TESTS */

/* toont alle Annonces van alle users */
SELECT * 
FROM UserAccount JOIN Annonce 
ON UserAccount.id = Annonce.user_Id;

/* toont alle Annonces van Joske */
SELECT tijdstip, omschrijving, prijs
FROM UserAccount JOIN Annonce
ON UserAccount.id = Annonce.user_id
WHERE UserAccount.id = 1;

/* toont alle Annonces van alle users met de naam 'Jefke' */
SELECT tijdstip, omschrijving, prijs
FROM UserAccount JOIN Annonce
ON UserAccount.id = Annonce.user_id
WHERE UserAccount.name = "Jefke";
```
