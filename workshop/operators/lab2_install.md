Use the IBM Cloud console to launch the OpenShift web console

![web console](../.gitbook/generic/webconsole.png)

First create an 'Example Bank' namespace

![create project](../.gitbook/generic/createproject.png)

From the navigation menu on the left select **Operators** --> **OperatorHub**

![operatorhub](../.gitbook/generic/operatorhub.png)

Type 'Postgres' into the search bar, and select the **PostgreSQL Operator by Dev4Ddevs.com** tile.

![postgres operator](../.gitbook/generic/postgresoperator.png)

Click **Continue** to show the community operator and then **Install**

![install operator](../.gitbook/generic/installoperator.png)

Be sure you are installing the Operator in the `Example Bank` namespace, and click **Subscribe**

![subscribe](../.gitbook/generic/subscribe.png)

Status will show "Succeeded: Up to date" when complete

![succeeded](../.gitbook/generic/subscribe.png)
