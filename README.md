# Kubernetes TD1

# Require
* Running kubernetes cluster
* Helm client

# Usage
### Deploy
`helm upgrade $APP_NAME . --install --namespace $NAMESPACE`
* Replace :
    * $APP_NAME : app name of the deployment
    * $NAMESPACE : desired namespace - if not exist, it will be created
    
### Customization
* values.yaml can be modified with desired config

### Expose
* You just want to expose this service temporarily ?
    * navigate to the pod on your Kubernetes Engine
    * expose it through a LoadBalancer with the 80 port
    * navigate to the LoadBalancer's IP
* Your cluster is accessible with a LoadBalancer in front of him ?
    * set the property ingress.enabled to true in the values.yaml file
    * set the correct host domain in ingress.hosts
    * upgrade
    * navigate to the domain name
    
### Namespace' quota
* You can inspect or increase quotas in the file : templates/quotas.yaml
* Quota actually set are more than sufficient to deploy 1 or 2 replica set of the docker hello world