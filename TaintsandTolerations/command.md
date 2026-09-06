
## Get more info on pods
$ k get pods -o wide

## To taint a node
kubectl taint nodes minikube key1=value1:NoSchedule

## Delete the pod by deleting the yaml file that produce the pod
 k delete -f nginx.yaml

## To untaint a node
kubectl taint nodes minikube key1=value1:NoSchedule-

## To add toleration to the yaml file?
tolerations:
- key: "key1"
  operator: "Equal"
  value: "value1"
  effect: "NoSchedule"

## Generating dry run service yaml file
kubectl expose pod nginx --type=LoadBalancer --port=80 --target-port=80 --name=myownservice --dry-run=client -o yaml > myownservice.yaml
