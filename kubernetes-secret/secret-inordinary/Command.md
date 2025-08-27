## Imparative command to create secret
kubectl create secret generic secretname --from-literal=username1=dXNlcm5hbWU= --from-literal=password1=dXNlcm5hbWU=
How do we use secrets in real time applications
How do we consume secrets and how do we create secrets
How do we retrieve these secrets and use it securely in our applications

Now to create secrets use use create_secrets.yaml file

Consume the secrets using the volume.yaml file on aws eks cluster


Once this has been done 
There two ways of creating the secrets one is
—- imperative commands and the other is 
—-using yaml file
## Command to describe secret
k describe secret db-user-pass -o -yaml
## To get secret
 k get secret
## To get additional information on secret
 k get secret -o yaml

 ## How to decypt a secret
 $ echo 'b3NhZ2llZmU=' | base64 --decode
