Let us get your OpenShift cluster in the correct state.

## 1. Target your cluster

Log in to your IBM Cloud account and navigate to the overview page for your OpenShift cluster. Click on the **OpenShift web console** button in the upper right corner. On web console, click the menu in the upper right corner (the label contains your email address), and select **Copy Login Command**. Paste the command into your local console window. It should resemble the following example:

```
oc login https://c100-e.us-east.containers.cloud.ibm.com:XXXXX --token=XXXXXXXXXXXXXXXXXXXXXXXXXX
```

## 2. Login to IBM Cloud

```
ibmcloud login -u <account name>
```

remember to use account "1": this is where we will create an AppID instance (if you do not already have one...)


## 3. Clone the repo

```
git clone https://github.com/IBM/example-bank.git
```

## 4. re-create the `example-bank` project

If you have been with us for any part of the lab track, I am sorry to say you will need to delete your hard earned work!

```
oc delete project example-bank
```

Otherwise, everyone please execute:

```
oc new-project example-bank
```

## 5. Install the PostgreSQL Operator and start an instance of a database

```
cd example-bank/scripts
./deploy-db.sh
```

## 6. Create an AppID instance

```
./createappid.sh
```

pay attention to the result of this script: you will need the Management URL and API Key for the next command.  If you already have an instance of AppID, you can retrieve the values you need using `ibmcloud resource service-key appid-example-bank-credentials`

## 7. Create Secrets

```
./createsecrets.sh <ManagementURL> <APIKey>
```

## 8. Apply schema

Once your database is running:

```
cd ..
oc apply -f data_model/job.yaml
```


