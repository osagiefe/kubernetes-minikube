## to start minkube the single node kubernetes cluster run the command below

minikube start
alias k=kubectl
k get nodes
k get pods 
k get po
k create ns test OR k create namespace test
k apply -f deployment.yaml
k apply -f service.yaml 

# when you delete a deployment file you authomatically deletes the pods
k delete -f deployment.yaml 
k delete -f service.yaml 
## create the file in test namaspace
k apply -f deployment.yaml -n test
k apply -f service.yaml -n test

# delete pods 
k delete pod <podname>

# check the pods created in that namespace
k get pods -n test

k get events

k describe svc nginx  -n test
k get svc -n test 

# # troubleshooting


k get pods -n test

k logs jenkins-6fb994cfc5-twnvn -n test

# to run nginx on the browser run the command within the test namespace

 minikube service nginx -n test


 ## Error and Challenges
 Deploying an application can fail with "ImagepullBackoff
" or "ErrorimagePull" Usually the image specified in the manifest file is not correct or the image is not found in Dockerhub or ECR. To troubleshoot this errors, use "k get events" and "k describe pod <podname>" commands 

# Error Type 2:
If a buggy application is built and saved to Dockerhub and such image is deployed with kebernetes a resulting common error message type is "crashloopbackoff"
 =====================================================