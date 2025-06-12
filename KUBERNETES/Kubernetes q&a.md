Kubernetes

1) Explain the Architecture of k8s
2) difference between deployment vs statefulset
3) what is namespace
4) what are the different services in k8s
5) what are the types of deployment stratagies of k8s
6) what is ingress in k8s, and how can we access applications deployed on-premies


senerio based questions:

## Scenerio 1
* your company is migrating its monolithic applications to a microservices architecture on kubernetes. how would you plan and execute this migration ?

### Task : Migrating Monolithic application to Microservices
**ANSWER**
1. Access the monolithic application to identify microservices.
2. Define container images and kubernetes deployment configurations.
3. set up a kubernetes cluster on-permises or using a cloud provider
4. Deploy microservices to the cluster with proper networking 
5. Implement monitoring and logging solutions.
6. Decompose the monolithic app into microservices gradually

## Scenerio 2
* you have a stateful application that requires persistent storage in k8s, how would you configure persistent storage 
for this application

### TASK : Configuring Persistent volume for Stateful Applicataion
**Answer**:
1. Define PersistentVolume (PV) and PersistentVolumeClaim (PVC) in YAML.
2. Choose an appropriate storage class.
3. Specify access mode, capacity, and other parameters in PCV.
4. Attach PVC to pods in their YAML manifests.
5. Deploy pods to kubernetes cluster, ensuring access to persistent storage.

## Scenerio 3
* your are experiencing performance issue with your k8s cluster. how would you diagnose and resolve these issues?

### TASK : Diagnosing Peerformance Issues in Kubernetes Cluster
**ANSWER**:
1. Monitor resource utilization: CPU, memory, Disk.
2. Use kubernetes dashboard or monitoring tools
3. check logs of individual pods for errors
4. scale up cluster by adding more worker nodes if needed.
5. Optimize resources requests and limits for pods.
6. Implement horizontal pods autoscaling

## Scenerio 4
* you need to deploy a k8s application across multiple environments (dev, staging, production) 
with different configuration, how would you manage environment-specific configurations in k8s ?

### TASK : Managing Environment-specific configurations
**Answer**:
1. Use ConfigMaps to store environment-specific config data.
2. Create seperate ConfigMaps for each environment.
3. Reference ConfigMaps in pod deployment configs using env varaible or volume mounts.
4. Use kubernetes namespaces to isloate resources.
5. Utilize tools like Helm for templating and managing manifests.

## Scenerio 5
* your teams wants to implement rolling updates for k8s deployment to minimize downtime during application upgrades, How would you achieve this ?

### TASK : Implementing Rolling Updates for kubernetes Deployment
**Answer**:
1. Define a new version of the container image.
2. Update the deployment configuration to use the new image.
3. Set deployment strategy to "RollingUpdate".
4. Specify maxSurge and maxUnavailable parameters.
5. Apply updated deployment config to the cluster.
6. Monitor rollout progress and rollback of needed.

