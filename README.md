# kubernetes-minikube
This is a kubernetes-minikube project. A single node clutter container orchestration tool use for deployment simple web project. Minikube is particulary suited for developemental use case only and should never be use for production grade project or environment.
With a Yaml Manifest file and a service yaml file specified, I succesfully deployed a nginx containerized application whose image is stored in Docker repository.
 # Output Nginx Page
![Image](https://github.com/user-attachments/assets/265a5c86-f182-489c-b094-4f955f73cbd0)

# Error and Challenges
 Deploying an application can fail with "ImagepullBackoff
" or "ErrorimagePull" Usually the image specified in the manifest file is not correct or the image is not found in Dockerhub or ECR. To troubleshoot this errors, use "k get events" and "k describe pod <podname>" commands and correct the issue and redeploy app after deleting previous pods 

# Error Type 2:
If a buggy application is built and saved to Dockerhub, when that image is deployed with kebernetes whithout first correcting the code bug, a resulting common error message type is "crashloopbackoff"
