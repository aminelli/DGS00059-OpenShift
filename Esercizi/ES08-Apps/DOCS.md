


```sh
oc login $API_SERVER --username kubeadmin --password $KUBE_VAR
oc get svc
oc expose service webapp-app-service
```