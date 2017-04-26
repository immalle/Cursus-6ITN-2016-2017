

```
create schema gip_taak_08_voorbeeld;
use gip_taak_08_voorbeeld;

create table UserAccount(
    id int not null auto_increment primary key,
    name text not null,
    email text
);

create table UserInfo(
    id int not null auto_increment primary key,
    user_id int not null,
    adres text,
    postcode text
);

insert into UserAccount(id, name, email)
values 
(1, "Joske", "joske@immalle.be"),
(2, "Jefke", "jefke@immalle.be");

insert into UserInfo(id, user_id, adres, postcode)
values
(1, 1, "Joske's adres", "2000"),
(2, 2, "Jefke's adres", "2010");


/* TESTS */

/* toont alle info over alle users */
SELECT * 
FROM UserAccount JOIN UserInfo 
ON UserAccount.id = UserInfo.user_Id;

/* toont alle NUTTIGE info over alle users, zonder de database-id's */
SELECT name, email, adres, postcode
FROM UserAccount JOIN UserInfo 
ON UserAccount.id = UserInfo.user_Id;
```