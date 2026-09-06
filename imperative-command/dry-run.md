## Dry run yaml file 
k run nginx --image=nginx:1.14.2 --dry-run=client -o yaml >felix.yaml

## Service for exposing pod created
 kubectl expose pod nginx --type=LoadBalancer --port=80 --target-port=80 --name=felixservice --dry-run=client -o yaml > felixservice.yaml
## applying pod
k apply -f felix.yaml

## Get pods
k get pods

## exposing application
k apply felixservice.yaml

## Get service
k get service felixservice

## minikube service
minikube service felixservice
## Exec in pod
k exec -it nginx -- sh
## Exiting pod
exit
## Deleting service
k delete -f felixservice.yaml 

## deleting pod
k delete -f felix.yaml

