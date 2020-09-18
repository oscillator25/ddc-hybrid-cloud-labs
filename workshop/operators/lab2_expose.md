expose the database

```
$ oc expose deploy creditdb --port=5432 --target-port=5432 --type=LoadBalancer --name my-pg-svc
```

```
oc get svc
```

take the external ip address and connect to it

```
docker run -it --rm postgres psql -h <ip> -U postgres
```

```
\c example
\dt *.
```

