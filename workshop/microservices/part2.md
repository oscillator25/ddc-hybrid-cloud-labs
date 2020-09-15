# Part 2

In this 

> Update YAML deployment manifests to point at correct images:


```
1. data_model/job.yaml => anthonyamanse/lab-data:1.0

2. bank-app-backend/transaction-service/deployment.yaml ==> anthonyamanse/lab-transaction:1.0

3. bank-app-backend/user-service/deployment.yaml ==> anthonyamanse/lab-user:1.0

4. bank-user-cleanup-utility/job.yaml ==> anthonyamanse/lab-erasure:1.0
```

* Note: The mobile simulator is already deployed.

> Run database schema job.

```
    cd data_model
    oc apply -f job.yaml
```

> Verify that the database schema load succeeded.

```
theia@theiadocker-koyfman1:/home/project/example-bank/data_model$ oc logs cc-schema-load-<pod name>
```

Output will resemble:
```
postgresql-operator-58cb79c899-69qpn   1/1     Running     0          99m
theia@theiadocker-koyfman1:/home/project/example-bank/data_model$ oc logs cc-schema-load-9tz6f
CREATE EXTENSION
CREATE DATABASE
You are now connected to database "example" as user "postgres".
CREATE SCHEMA
SET
CREATE TABLE
CREATE TABLE
CREATE TABLE
CREATE TABLE
```

> Now, we can deploy the services:
```
oc apply -f bank-app-backend/user-service/deployment.yaml -f bank-app-backend/transaction-service/deployment.yaml -f bank-user-cleanup-utility/job.yaml
```

> Wait until deployments are complete.

Find route to access simulator:

```
theia@theiadocker-koyfman1:/home/project/example-bank$ oc get routes | grep simulator
```
