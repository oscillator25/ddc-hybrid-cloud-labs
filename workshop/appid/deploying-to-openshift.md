# Deploying to OpenShift

## Verify deployment file

Open **deployment.yaml** file in the root folder. Change the configuration to use the image you just built.

```yaml
containers:
  - image: <YOUR_DOCKER_HUB>/workshop-mobile-simulator:1.0
```

## Deploy to OpenShift

To deploy, you can use `oc apply` with the deployment file.

```bash
$ oc apply -f deployment.yaml
```

## Check status

Check the status of the pods. Make sure the status is **Running**. You can also check its logs using `oc logs <podname>`

```bash
$ oc get pods

NAME                                           READY   STATUS    RESTARTS   AGE
mobile-simulator-deployment-5b7bb5f56f-qvrj7   1/1     Running   0          15s
```