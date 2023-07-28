# Kubernetes (K8)

### What is K8?

```
Kubernetes is an open-source container orchestration platform designed to automate the deployment, scaling, and management of containerized applications, making it easier to manage complex microservices-based architectures.
```

### K8 Architecture 

![Alt text](images/K8.jpg)

### Why should you learn and use K8?

```
- scaleable and Highly Available 

- excels at managing microservices 

- automation 

- cloud native dev practices

- portable; consistency across env, easy to move applications between cloud providers or on prem.

- large active community for extensive support, documentation and add ons

- industry standard and future proof; widely used by industry, in demand skills and enhaces career prospect.

```

### Who is using K8?
```
- AWS, Azure and Google.

- Apple, Uber, Netflix and VW
```
### benifits to business?

```
Cost Efficiency: 

Faster Deployment: 

Improved Resource Management: Efficiently manage and allocate resources, leading to better utilization and cost savings.

Streamlined Operations: Automate repetitive tasks, reducing manual intervention and freeing up IT teams for higher-value activities.

Enhanced Developer Productivity: Empower developers with a self-service platform, allowing them to focus on coding rather than infrastructure.

Support for Microservices: Facilitate the adoption of microservices architecture, enabling more modular and flexible application development.

Competitive Advantage: Embrace containerization and modern application development practices, staying ahead in the market.

Ecosystem and Support: Benefit from a robust ecosystem, vast community support, and a wide range of tools and integrations.
```

### what are K8 objects - Pods - Deployment/s - Services - replica sets -

```

Pods:

Pods are the smallest deployable units in Kubernetes and represent a single instance of a running process within the cluster.

Deployments:

Deployments are higher-level abstractions that manage the lifecycle of Pods and provide declarative updates for application deployments

Services:

Services provide stable and abstracted endpoints for accessing a set of Pods.

ReplicaSets:

A ReplicaSet is an older version of the Deployment object and is responsible for ensuring a specified number of replicas (Pod instances) are running and maintained.
```

### Concept of labels and selectors in K8
```

Labels are key-value pairs attached to Kubernetes resources like Pods, Services, Deployments, ReplicaSets, etc.


Selectors are used to "select" or filter resources based on their labels

There are two types of selectors:
Equality-Based Selectors: These match resources whose labels have specific key-value pairs.

Set-Based Selectors: These match resources using a set of label requirements (AND, OR, NOT conditions).
```

# Deployment for nginx

### step 1 - Create file yml for nginx
```
nano nginx-k8.yml
```
```
apiVersion: apps/v1 # which api to use for deployment
kind: Deployment # pod - service what kind of service/object you want to create

 

# what would you like to call it - name the service/object
metadata:
  name: nginx-deployment # naming the deployment

 

spec:
  selector:
    matchLabels:
      app: nginx # look for this label to match with k8 service
    # Let's create replica set of this with instances/pods
  replicas: 3 # 3 pods
    # template to use its label for k8 service to launch in the browser
  template:
    metadata:
      labels:
        app: nginx # This label connects to
                   # the service or any other k8 components
  # Let's define the container spec
    spec:
      containers:
      - name: nginx
        image: ks241/tech241-nginx:v2
        ports:
        - containerPort: 80


```

### step 2 create deployment 

```
kubectl create -f nginx-k8.yml

```
### step 3 - check deployment 

```
kubectl get deployment
```

### step 4 - to delete deployment in k8

```
kubectl delete deployment nginx-k8.yml
```

### create yml file for nodejs

```
nodejs-k8.yml

```
```
apiVersion: apps/v1 # which api to use for deployment
kind: Deployment # pod - service what kind of service/object you want to create

 

# what would you like to call it - name the service/object
metadata:
  name: nodejs-deployment # naming the deployment

 

spec:
  selector:
    matchLabels:
      app: nodejs # look for this label to match with k8 service
    # Let's create replica set of this with instances/pods
  replicas: 3 # 3 pods
    # template to use its label for k8 service to launch in the browser
  template:
    metadata:
      labels:
        app: nodejs # This label connects to
                   # the service or any other k8 components
  # Let's define the container spec
    spec:
      containers:
      - name: nodejs
        image: ks241/tech241-nodejs:v1
        ports:
        - containerPort: 3000


```

### step create deployment 

```
kubectl create -f nodejs-k8.yml

```
### step - check deployment 

```
kubectl get deployment
```

![Alt text](<images/k8 get deployment.png>)

