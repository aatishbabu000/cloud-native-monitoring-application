# cloud-native-monitoring-application
All the steps and cmd

Cloud Native Resource Monitoring Python App on K8s!
Python and How to create Monitoring Application in Python using Flask and psutil
How to run a Python App locally.
Creating Dockerfile
Building DockerImage
Running Docker Container
Docker Commands
Create ECR repository using Python Boto3 and pushing Docker Image to ECR
Create Kubernetes Deployments and Services using Python!

Install dependencies

The application uses the **`psutil`** and **`Flask`, Plotly, boto3** libraries. Install them using pip:

pip3 install -r requirements.txt


Run the application

To run the application, navigate to the root directory of the project and execute the following command:

$ python3 app.py


This will start the Flask server on **`localhost:5000`**. Navigate to [http://localhost:5000/](http://localhost:5000/) on your browser to access the application.

Dockerizing the Flask application

Create a Dockerfile

$ docker build -t <image_name> .


Run the Docker container

To run the Docker container, execute the following command:

$ docker run -p 5000:5000 <image_name>


This will start the Flask server in a Docker container on **`localhost:5000`**. Navigate to [http://localhost:5000/](http://localhost:5000/) on your browser to access the application.


Create an ECR repository using Python:

import boto3

Create an ECR client
ecr_client = boto3.client('ecr')

Create a new ECR repository
repository_name = 'my-ecr-repo' response = ecr_client.create_repository(repositoryName=repository_name)

Print the repository URI
repository_uri = response['repository']['repositoryUri'] print(repository_uri)


Push the Docker image to ECR

Push the Docker image to ECR using the push commands on the console:

$ docker push <ecr_repo_uri>:


Check by running following commands:

kubectl get deployment -n default (check deployments)
kubectl get service -n default (check service)
kubectl get pods -n default (to check the pods)
Once your pod is up and running, run the port-forward to expose the service

kubectl port-forward service/<service_name> 5000:5000
