# Prerequisites
this repo

# How to use

This image will support Cassandra applications using the Python driver.

# Driver test

You can do something like the following to do a test of your setup.

```
from cassandra.cluster import Cluster

cluster = Cluster(['172.16.238.2', '172.16.238.3', '172.16.238.4'])

session = cluster.connect()

rows = session.execute('SELECT * from system_auth.roles')

for role in rows:
    print role.role, role.is_superuser


```

Note that once you print a result, you'll need to reload rows.