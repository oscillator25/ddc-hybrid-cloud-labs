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

