expose the database

```
$ oc expose deploy creditdb --port=5432 --target-port=5432 --type=LoadBalancer --name my-pg-svc
```

to find the external ip address of the database

```
oc get svc
```

copy the external ip address of the my-pg-svc service and connect to it.  password is `postgres`

```
docker run -it --rm postgres psql -h <ip> -U postgres
```

verify database tables

```
\c example
\dt *.
```

