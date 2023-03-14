# f5-cis-method-ingress

This is the steps on how to deploy F5 CIS via Ingress method

## Deploy and Expose your app in the Kubernetes cluster

You can deploy your own app or you can use the service/deployment yaml files below for testing

```bash
kubectl apply -f appresources/
```
...

## INSTALL CIS MANUALLY

...

kubectl create secret generic f5-bigip-ctlr-login -n kube-system --from-literal=username=admin --from-literal=password=<password>
kubectl create serviceaccount bigip-ctlr -n kube-system
