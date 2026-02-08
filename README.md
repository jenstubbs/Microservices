Lab 2

# Task 2
## Step 2 
<img width="621" height="66" alt="Screenshot 2026-02-07 at 5 26 00 PM" src="https://github.com/user-attachments/assets/a3e23708-677c-40db-b744-e62ddf8265d4" />

- This screenshot show the current Google Cloud project my gcloud CLI is using.  It is important because all resources are created inside Lab 2. 


## Step 3 
<img width="625" height="47" alt="Screenshot 2026-02-07 at 5 27 28 PM" src="https://github.com/user-attachments/assets/89bcc797-c4ba-4ffc-a4ef-46d421a7b2f5" />

- This shows the default zone configured in g cloud, the zone determines where resources like clusters and VM’s are geographically.  

## Step 4 
<img width="623" height="26" alt="Screenshot 2026-02-07 at 5 28 15 PM" src="https://github.com/user-attachments/assets/407e2b79-90cb-4de1-a6e4-a312e59cda5f" />


- This shows the default zone was set to us-east1-b.  This is so you dont have to specify each zone. 

## Step 5 
<img width="623" height="185" alt="Screenshot 2026-02-07 at 5 28 55 PM" src="https://github.com/user-attachments/assets/01c4122a-dac5-45b6-9c59-8318c1bcde0a" />

<img width="626" height="151" alt="Screenshot 2026-02-07 at 5 29 32 PM" src="https://github.com/user-attachments/assets/fd82ddd4-161c-4c9d-a6c6-2766504d5060" />

- These screenshots show the creation of a google Kubernetes engine cluster named gke-cluster.  num-nodes creates three worker nodes and the machine-type defines the VM size.
## Step 6 
<img width="622" height="46" alt="Screenshot 2026-02-07 at 5 30 17 PM" src="https://github.com/user-attachments/assets/9137bcc9-d07f-41ca-b59f-66f5bf7a2f52" />

- This shows the configuration of Kubectl to communicate with the clusters.  It downloads credentials and updates commands to target that cluster.
## Step 7 
<img width="623" height="63" alt="Screenshot 2026-02-07 at 5 30 49 PM" src="https://github.com/user-attachments/assets/1136ee6c-3d4b-4e4a-b759-2f903b221065" />

- This shows the worker nodes in the cluster and their status.  This confirms the cluster is healthy and ready to run pods.  

# Task 3
## Step 0
<img width="623" height="209" alt="Screenshot 2026-02-07 at 5 31 49 PM" src="https://github.com/user-attachments/assets/60fba8ff-93ab-48da-945b-9547a9ea6022" />

- This opens a browser to authenticate your google account so gcloud can access the project and resources.
## Step 1 
<img width="624" height="51" alt="Screenshot 2026-02-07 at 5 32 32 PM" src="https://github.com/user-attachments/assets/157d9e25-5c6c-4699-a44e-a0194267a4f0" />

- This creates a pod named nginx running the nginx container image.

## Step 2 
<img width="628" height="47" alt="Screenshot 2026-02-07 at 5 32 54 PM" src="https://github.com/user-attachments/assets/9580730f-27e7-48ba-95c4-afaa68161057" />

- This creates another pod called server, it is the “server” other pods will connect to.  

## Step 3 
<img width="625" height="47" alt="Screenshot 2026-02-07 at 5 33 22 PM" src="https://github.com/user-attachments/assets/3f7f7130-8681-4383-a3d0-95550886b36a" />

- Creates a pod called ‘client’, used to test connectivity to the server pod.  

## Step 4 
<img width="626" height="125" alt="Screenshot 2026-02-07 at 5 33 49 PM" src="https://github.com/user-attachments/assets/c2480a73-d6c8-4a22-a328-b80009a53870" />

- Lists all the pods in the current namespace and shows whether they’re running.  

## Step 5 
<img width="626" height="68" alt="Screenshot 2026-02-07 at 5 34 15 PM" src="https://github.com/user-attachments/assets/c2cd6c0e-9e87-4829-a01c-12dc33063c36" />

- This also shows the cluster nodes, but allows us to confirm the cluster health while working on them. 

## Step 6 
<img width="623" height="227" alt="Screenshot 2026-02-07 at 5 34 42 PM" src="https://github.com/user-attachments/assets/e8d9029f-ec71-4e2d-b59e-c6d7e4526442" />

-This runs the command to curl localhost inside the server pod, checks that nginx is running and responding.  

## Step 7 
<img width="627" height="63" alt="Screenshot 2026-02-07 at 5 35 06 PM" src="https://github.com/user-attachments/assets/622e85bf-e3e9-4835-b0ac-39354383b310" />

- This shows detailed information about the server pod and filters for the pod IP address, which allows for direct pod to pod communication.

## Step 8 
<img width="626" height="333" alt="Screenshot 2026-02-07 at 5 35 34 PM" src="https://github.com/user-attachments/assets/26c7ea93-8933-4657-a36d-7bb161dec2a8" />

- This runs curl from inside the client pod to the server pod’s IP to test network connectivity between pods. 

# Task 4 
## Step 1
<img width="622" height="83" alt="Screenshot 2026-02-07 at 5 36 39 PM" src="https://github.com/user-attachments/assets/7413b361-1bc6-4980-b514-6915208daff5" />

- Creates a service named ‘server-service’ that exposes the server pod and provides a stable IP, DNS name, and load balancing across pods.

## Step 2 
<img width="627" height="66" alt="Screenshot 2026-02-07 at 5 37 04 PM" src="https://github.com/user-attachments/assets/2b75d66a-e75d-41bb-86ed-72468b4a0c93" />

- Lists all services and their clusters IP addresses.

## Step 3 
<img width="628" height="236" alt="Screenshot 2026-02-07 at 5 37 28 PM" src="https://github.com/user-attachments/assets/117f03cf-7515-463b-aff0-d788dd94b55e" />

- Shows detailed information about the service, with endpoints and ports, to verify it’s correctly linked to server pod.  

# Task 5 
## Step 1
<img width="626" height="99" alt="Screenshot 2026-02-07 at 5 39 03 PM" src="https://github.com/user-attachments/assets/5b4c747d-9f0e-44c4-a010-f03ffa1770f3" />

- This creates a temporary pod running BusyBox that sleeps for an hour.

## Step 2 
<img width="624" height="212" alt="Screenshot 2026-02-07 at 5 39 33 PM" src="https://github.com/user-attachments/assets/e85f67f7-3c00-45ef-b3bf-9341771316c4" />

- This runs a DNS lookup from inside the cluster to confirm that Kubernetes DNS resolves server-service to the service’s cluster IP.

# Task 6 
## Step 1 
<img width="627" height="345" alt="Screenshot 2026-02-07 at 5 42 21 PM" src="https://github.com/user-attachments/assets/dec418a6-5344-46e9-9533-e55d24759ec3" />

- Tests connectivity using the service name instead of an IP.  This demonstrates how Kubernetes services and DNS make communication stable and easier.  

## Step 2 
<img width="629" height="347" alt="Screenshot 2026-02-07 at 5 42 51 PM" src="https://github.com/user-attachments/assets/4e561d9b-f62c-431d-a56c-4a6add8eb1e9" />

- This command was ran three times.  Tests connectivity using the service name instead of an IP.  This demonstrates how Kubernetes services and DNS make communication stable and easier.

# Task 7 
<img width="628" height="282" alt="Screenshot 2026-02-07 at 5 43 40 PM" src="https://github.com/user-attachments/assets/8a25f509-4163-4c5a-ba10-dfc90d2737ea" />

- This screenshot shows the clean up steps taken to clear out the kubbernetes and pods created during this lab.

# Task 8 
## 1. 
- Before Kubernetes, multiple containers could be managed using Docker CLI scripts or Dockers compose.  It allowed developers to start and connect containers, configure networks, and define services.  Challeneges that could arise when containers increase is manual scaling, which is difficult.  Also managing multiple hosts can become complex.  

## 2. 
- A pod is the smallest deployable unit in Kubernetes and usually contains one or more containers, which share networks and storage volumes.  Kubernetes treats pods as the smallest unit because they are meant to work very closely.  Kubernetes can not manage containers directly because containers depend on storage.  Managing pods simplifies deployment, scalability, and communicaiton.

## 3. 
- Services are nessecary because pods are temporary and their IP addresses can change whenever they are recreated.  A service allows for stable IP adresses, automatic load balancing, and gives consistency for application communicaiton.  It is essential to microservices architectures because many services need reliable communication and allow applications to find eachother without individual IP adresses.

## 4. 
- DNS-based service discovery works in Kubernetes because each service is assigned a DNS name that map to the service's IP address.  Service discovery is a core requiremet because services are constantly evolving, locations change frequently, and applications need reliable communication.

## 5. 
- I believe it is more effective to run applicaitons as multiple containerized services managed by kubernetes.  Services can be scaled independetly, instead of the whole application.  If one pod or container fails, Kubernetes will restart it or replace it.  Kubernetes provides built in communication between services.  All in all Kubernetes is easier to manage complex applications.


## Kubernetes Diagram 
<img width="321" height="521" alt="Screenshot 2026-02-07 at 7 08 20 PM" src="https://github.com/user-attachments/assets/9924328e-5aff-4db3-8c51-bc7658e6db08" />




