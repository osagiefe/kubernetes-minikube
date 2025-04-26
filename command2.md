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
# Scaling up pods
k scale --replicas=3 -f <ginx2-deployment.yaml>

# Command to update image 
kubectl set image deployment nginx-deployment nginx=nginx:1.12.0

# Get endpoint connection 
k get endpoints nginx-service

# # troubleshooting

k get pods -n test

k logs jenkins-6fb994cfc5-twnvn -n test

# to run nginx on the browser run the command within the test namespace

 minikube service nginx -n test


 ## Error and Challenges
 Deploying an application can fail with "ImagepullBackoff
" or "ErrorimagePull" Usually the image specified in the manifest file is not correct or the image is not found in Dockerhub or ECR. To troubleshoot this errors, use "k get events" and "k describe pod <podname>" commands 

# Error Type 2:
If a buggy application is built and saved to Dockerhub and such image is deployed with kebernetes a resulting common error message type is "crashloopbackoff". Solution: Ensure verify code is bug free by running it locally before deployment

## Error OOMKilled
When there is memory leakage: meaning a container is trying to access allocated memory or the node is running out of memory. 
Solution:
1. review memory limits defined in yaml file to ensure it is sufficient for workload
2. Increase memory allocated to pods or node
3. Examine logs to see which container is problematic
4. Use name space to segregate or distribute pods
5. Scale application horizontally across multiple nodes to distribut  memory workload 

 =====================================================