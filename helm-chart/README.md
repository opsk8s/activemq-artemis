# Active MQ

install:

```shell

# Localhost
helm upgrade -i -n chat -f values.yaml --set artemisPassword="admin" --set url="localhost" c . 

```
