This is an Ubuntu 16.04 Docker image running [Cassandra 3.7 instaclustr](https://github.com/instaclustr/cassandra.git "Cassandra 3.7 instaclustr").

Build
-----
To build the machine run:
~~~~
docker build -t ubuntu:cassandra3.7 .
~~~~

Run
---

~~~~
docker run -t -i  ubuntu:cassandra3.7 /bin/bash
~~~~


