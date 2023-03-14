# f5-cis-method-ingress

DEPLOY APP

...

INSTALL CIS MANUALLY

...

kubectl create secret generic f5-bigip-ctlr-login -n kube-system --from-literal=username=admin --from-literal=password=<password>
kubectl create serviceaccount bigip-ctlr -n kube-system
