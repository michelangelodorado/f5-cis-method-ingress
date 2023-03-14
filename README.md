# f5-cis-method-ingress

This is the steps on how to deploy F5 CIS via Ingress method

Mandatory requirements for deploying CIS:

- Kubernetes Cluster must be up and running.
- AS3: 3.18+ must be installed on your BIG-IP system https://clouddocs.f5.com/products/extensions/f5-appsvcs-extension/latest/userguide/installation.html
- Create a BIG-IP partition to manage Kubernetes objects. This partition can be created either via the GUI (System > Users > Partition List) or via our TMOS CLI: (tmsh create auth partition <cis_managed_partition>)
- You need a user with administrative access to this partition.

## Deploy and Expose your app in the Kubernetes cluster

You can deploy your own app or you can use the service/deployment yaml files below for testing

```bash
git clone https://github.com/michelangelodorado/f5-cis-method-ingress.git
cd f5-cis-method-ingress
kubectl apply -f appresources/
```

## Install F5 CIS

```bash
kubectl create secret generic f5-bigip-ctlr-login -n kube-system --from-literal=username=admin --from-literal=password=<password>
kubectl create serviceaccount bigip-ctlr -n kube-system
```
