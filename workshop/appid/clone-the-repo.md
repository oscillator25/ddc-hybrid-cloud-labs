# Clone the repo

## Clone the example-bank repo

Clone the repo **example-bank** if you haven't yet

```
$ git clone https://github.com/IBM/example-bank
$ cd example-bank
```

## Login with ibmcloud and oc cli

Log in your IBM Cloud account with the `ibmcloud` cli

*Make sure to use your personal account when it asks you*

```text
$ ibmcloud login -u YOUR_IBM_CLOUD_EMAIL
```

Log in with the OpenShift cluster provided for you using the OpenShift console. On the upper right corner, click your account and then click on `Copy Login Command`. This should open a new window and show you the command to login with the `oc` cli

![IBM Cloud dashboard](../.gitbook/generic/webconsole.png)

![OpenShift Console](../.gitbook/generic/image%20%283%29.png)

Create a project named **example-bank** for the resources you'll deploy.

```text
$ oc new-project example-bank
```

Also, make sure you are using the **example-bank** project.

```text
$ oc project example-bank
```