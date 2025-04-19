## to start minkube the single node kubernetes cluster run the command below

minikube start
alias k=kubectl
k get nodes
k get pods 
k get po
k create namespace test
k apply -f deployment.yaml
k apply -f service.yaml 

# when you delete a deployment file you authomatically detes the pods
k delete -f deployment.yaml 
k delete -f service.yaml 
## create the file in test namaspace
k apply -f deployment.yaml -n test
k apply -f service.yaml -n test

#delete pods 
k delete pod <podname>

# check the pods created in that namespace
k get pods -n test

k get events

k describe svc nginx  -n test
k get svc -n test 

# # troubleshooting

k get nodes -o wide
k get pods -n test

k logs jenkins-6fb994cfc5-twnvn -n test

# to run nginx on the browser run the command within the test namespace

 minikube service nginx -n test


 ## =========================================================