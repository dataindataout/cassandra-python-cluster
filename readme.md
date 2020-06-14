# Prerequisites
this repo

# How to use

This cluster will support Cassandra applications using the Python driver.

# Driver demo

You can do something like the following on the app container to do a test of your setup. 

This is also a neat demonstration of Cassandra querying different nodes.

```
python3

from cassandra.cluster import Cluster

cluster = Cluster(['172.16.238.2', '172.16.238.3', '172.16.238.4'])

session = cluster.connect()

peers = session.execute('SELECT * from system.peers')

for peer in peers:
    print(peer.peer, peer.data_center)

```
