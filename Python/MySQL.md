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


