# MySQL

Installeer de mysql-connector:

```
pip install mysql-connector
```

Test uit met volgende code (b.v. in Jupyter):

```
import mysql.connector

def connect_db():
  config = {
    'user':'imma',
    'password':'imma',
    'host':'localhost',
    'database':'thewall'
  }
  cnx = mysql.connector.connect(**config)
  return cnx

def close_db(cnx):
  cnx.close()

def get_db(cnx):
  cursor = cnx.cursor()
  cursor.execute("SELECT * FROM messages")
  
  for(id, inhoud, tijdstip) in cursor:
    print('{} ({}): {}'.format(id, tijdstip, inhoud))
    
  cursor.close()

def get_messages():
  c = connect_db()
  get_db(c)
  close_db(c)
```

Uitleg van de code:

1. De method `connect_db` maakt een dictionary met config-settings
   en returnt een connection-object.
2. De method `close_db` sluit de connectie geassocieerd met een
   connection-object.
3. De method `get_db` gebruik een `cursor` van het connection-object
   en itereert vervolgens met een for-loop over elke rij.
4. De method `get_messages` gebruikt bovenstaande methods.


# Opmerking

I.p.v. `mysql.connector` kan je ook `MySQLdb` gebruiken.
Zie ook http://stackoverflow.com/questions/32575857/the-differences-between-mysqldb-and-mysqlconnector
