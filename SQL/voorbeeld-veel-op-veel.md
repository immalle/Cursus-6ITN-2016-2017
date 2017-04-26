

```
create schema gip_taak_08_voorbeeld_veel_op_veel;
use gip_taak_08_voorbeeld_veel_op_veel;

create table Leerling(
    id int not null auto_increment primary key,
    name text not null,
    postcode text
);

create table Vak(
    id int not null auto_increment primary key,
    beschrijving text,
    leerkracht text
);

create table LeerlingVak(
    id int not null auto_increment primary key,
    leerling_id int,
    vak_id int
);

insert into Leerling(id, name, postcode)
values 
(1, "Joske", "2000"),
(2, "Jefke", "2010");

insert into Vak(id, beschrijving, leerkracht)
values
(1, "Wiskunde", "Lkr1"),
(2, "Nederlands", "Lkr2");

insert into LeerlingVak(id, leerling_id, vak_id)
values
(1, 1, 1),
(2, 2, 1),
(3, 1, 2),
(4, 2, 2);


/* TESTS */

/* TODO zeker met joins */
```