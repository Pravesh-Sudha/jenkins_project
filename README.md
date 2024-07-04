# Continuous Integraion/Continuous Deployment (CI/CD) project
## About the project
The core of the project is a simple "hello world" flask application(/app directory). 
However, the goal was on the example of this app make its integraion and deploemnt as 
automated and efficient as possible, according to DevOps principles. In other words,
in this application complete CI/CD pipeline was implemented.
## Frameworks and services used:
* GitHub
* AWS
* Jenkins
* Docker
* Kubernetes
* Flask
## CI/CD pipeline
### CI part
Each commit triggers a new Jenkins build of Docker image, followed by running test automatically. 
In case of failed tests pipeline stops and an error is rosen. In case of successful test,
the image is pushed to private Docker registry which is run on a separate AWS EC2 instance.
### CD part
After push of the docker image to the registry, deployment to K8s follows. Kubernetes run on 3 servers:
one is a control pane, the other two are worker nodes. 