# Continuous Integration/Continuous Deployment (CI/CD) project
## About the project
The core of the project is a simple "hello world" flask application(/app directory). 
However, the goal is to make integration and deployment of this app as automated and 
efficient as possible, according to DevOps principles. In other words, in this 
application complete CI/CD pipeline was implemented.
## Frameworks and services used:
* GitHub
* AWS
* Jenkins
* Docker
* Kubernetes
* Flask
## CI/CD pipeline
### CI part
Each commit triggers a new Jenkins build of the Docker image, followed by running 
the test automatically. In case of failed tests pipeline stops and an error is raised. 
In case of a successful test, the image is pushed to a private Docker registry which
is run on a separate AWS EC2 instance.
### CD part
After the push of the docker image to the registry, deployment to K8s follows. 
Kubernetes runs on 3 servers: one is a control pane, the other two are worker nodes.