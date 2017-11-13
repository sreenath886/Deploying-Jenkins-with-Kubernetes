# cicd-buzz
# jenkins-deployment.yaml
The file is defining a Deployment as indicated by the kind field.
The Deployment specifyies a single replica. This ensures one and only one instance will be maintained by the Replication Controller in the event of failure.
The container image name is jenkins and version is 2.32.2
The list of ports specified within the spec are a list of ports to expose from the container on the Pods IP address.
Jenkins running on (http) port 8080.
The Pod exposes the port 8080 of the jenkins container.
To create the deployment execute:

### kubectl create -f jenkins-deployment.yaml

To validate that creating the deployment was successful you can invoke:

### kubectl get deployments


# jenkins-service.yaml

The file is defining a Service as indicated by the kind field.
The Service is of type NodePort. Other options are ClusterIP (only accessible within the cluster) and LoadBalancer (IP address assigned by a cloud provider e.g. AWS Elastic IP).
The list of ports specified within the spec are a list of ports exposed by this service.
The port is the port that will be exposed by the service.
The target port is the port to access on the Pods targeted by this service. A port name may also be specified.
The selector specifies the selection criteria for the Pods targeted by this service.
To create the service execute:

### kubectl create -f jenkins-service.yaml
To validate that creating the service was successful you can invoke:

### kubectl get services