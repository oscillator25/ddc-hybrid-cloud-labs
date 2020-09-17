Use the IBM Cloud console to launch the OpenShift web console

First create an 'Example Bank' namespace

From the navigation menu on the left select **Operators** --> **OperatorHub**

Type 'Postgres' into the search bar, and select the **PostgreSQL Operator by Dev4Ddevs.com** tile.

Click **Continue** to show the community operator and then **Install**

Be sure you are installing the Operator in the `Example Bank` namespace, and click **Subscribe**

Status will show "Succeeded: Up to date" when complete

Use the very top drop down in the navigation menu on the left to switch to *Developer** view

Click **+Add** and select the Databse tile

Choose the **Database Database** tile and then **Create**

You can edit some of the specifics of the database here.  For example, change the name to `creditdb` and click **Create**

Switch to the Topology tab, and watch your database creation complete!

Now we will need some CLI access.  First, go to https://labs.cognitiveclass.ai and start a session

back on your OpenShift web console, click you email address in the upper right corner and choose **Copy Login Command**

From the resulting screen, grab your login credentials, and copy them into your ClognitiveClass terminal

switch to the example bank project

```
git clone https://github.com/IBM/example-bank
```

```
kubectl create secret generic bank-db-secret --from-literal=DB_SERVERNAME=<db_name> --from-literal=DB_PORTNUMBER=<db_port> --from-literal=DB_DATABASENAME=example --from-literal=DB_USER=<db_user> --from-literal=DB_PASSWORD=<db_password>
```

Run the script to create the schema

```
oc apply -f data_model/job.yaml
```

![schema](https://raw.githubusercontent.com/IBM/example-bank/main/images/schema-1.png)

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
