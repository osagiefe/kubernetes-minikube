A junior cloud engineer has been asked to use
imperative command to create the following:
* A pod called: nginx1
* Image name: nginx
* Namespace: dev
* Do not run the nginx server after provisioning
* Output yaml file to output.yaml
Solution: 
export do="--dry-run=client -o yaml"
k -n dev run nginx1 --image nginx $do >> output.yaml

# Question 2:
Now create a pod with the previous output file output.yaml
Solution:
k create -f output.yaml

# Question 3:
A junior cloud engineer has been asked to use
imperative command to create the following:
* A pod called: nginx2
* Image name: ngnix
* Namespace: dev
* Do not run the nginx server after provisioning
* Output yaml file to result.yaml

