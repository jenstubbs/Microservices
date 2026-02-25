# Lab 4
## Task 1A

### Step 1 
<img width="541" height="120" alt="Screenshot 2026-02-23 at 4 56 54 PM" src="https://github.com/user-attachments/assets/014b5623-c5c5-4f49-81c0-cef8755ca20e" />

- This command shows which google identity the CLI will use.  Gcloud reads stored Oauth credentials and without it wrong accounts will show permission errors. 

### Step 2 

<img width="853" height="212" alt="Screenshot 2026-02-23 at 4 57 33 PM" src="https://github.com/user-attachments/assets/db2942f9-5d9e-4dd7-8e39-a88cc2cda55f" />

- This command shows which project gcloud is targetting.  It reads the active configuration to which API calls go to.  If incorrect, your clusters will go to the wrong place.  


### Step 4 

<img width="840" height="245" alt="Screenshot 2026-02-23 at 5 01 07 PM" src="https://github.com/user-attachments/assets/c64ff224-0dab-4fcc-8be1-70f91f9f2675" />

- The first command is to set the default zone for your resources, whereas the second one is to verify the zone.  It is important to update and ensure your location as without the correct location you may end up with "cluster not found" as GKE commands assume a zone. 

### Step 5 
<img width="822" height="77" alt="Screenshot 2026-02-23 at 5 03 21 PM" src="https://github.com/user-attachments/assets/35a580c5-8423-44b0-9f9c-587f63c0448e" />

- This command is basically turning on certain features for the project.  GCP activates API's so the project can call them.  In this command we can call IAM policy management, creat clusters, and store container images.  Without it we really would not be able to do the lab.  

## Task 1B

### Step 1 & 2 

<img width="860" height="345" alt="Screenshot 2026-02-23 at 5 09 59 PM" src="https://github.com/user-attachments/assets/7c747d50-eddd-4ebf-b63f-afbf4f758b97" />

- The first command was to show if we have any clusters running and as you can see there was no response telling us we are able to move forward, avoiding cretaing the same thing voer again.  The second command is to create a Kubernetes cluster.  We have GKE provisions, setting up control plane, and configuring networks.  Without the the cluster, there would be no where to run th epods.  


### Step 3 

<img width="612" height="149" alt="Screenshot 2026-02-23 at 5 10 35 PM" src="https://github.com/user-attachments/assets/e256a562-e2a7-41f5-bacc-43b4188307f1" />

- This command confirms the cluster is running and actually exists.  Its important to verify the status before moving forward, so other commands can run smoothly.  

### Step 4 

<img width="807" height="69" alt="Screenshot 2026-02-23 at 5 11 02 PM" src="https://github.com/user-attachments/assets/bafeb184-357a-4e0f-a238-983595e30d5e" />

- This command is to connect Kubectl to this cluster.  it updates the cluster endpoints and authorization plugins.  It gives directions to kubectl to know which cluster to talk to.  
### Step 5 

<img width="735" height="76" alt="Screenshot 2026-02-23 at 5 11 36 PM" src="https://github.com/user-attachments/assets/94914245-754f-4437-af69-64f5bfa25297" />

- This command checks if Kubernetes is connecting to your machine.  Kubernetes API returns nodes and if nodes arent ready, pods can't schedule.

### Step 6 

<img width="490" height="35" alt="Screenshot 2026-02-23 at 5 16 55 PM" src="https://github.com/user-attachments/assets/076b5778-1d93-4b8e-ac7b-2a14c715f9cd" />

- This command checks the artifact registry repo location and without this we would not be able to push anything or push into the wrong place.  


## Task 2 
### Step 1 

<img width="593" height="92" alt="Screenshot 2026-02-23 at 5 18 04 PM" src="https://github.com/user-attachments/assets/907bcaab-60f5-4d70-bd87-2387b97683d5" />

- cd~ goes to the home directory, and cd gke-microservices-manifests goes to the folder containing the Kubernetes YAML's.  
### Step 2 
<img width="847" height="80" alt="Screenshot 2026-02-23 at 5 18 53 PM" src="https://github.com/user-attachments/assets/f43d025e-bfe5-49de-b829-f9053ef8e109" />

- This command declares "run products app" as a deployment.  Kubernetes is calling for the deployment controller to create a ReplicaSet, the ReplicaSet creates pods, and the scheduler places pods on nodes.  It is important becasue these are all steps in the deployment process.  

### Step 3 

<img width="777" height="45" alt="Screenshot 2026-02-23 at 5 19 18 PM" src="https://github.com/user-attachments/assets/78733bbd-bbfd-4ac1-af30-16d9a760b800" />

- This command is deploying orders.  Kubernetes is creates the object declared inside.  At this point we can see multiple services communicating.  


### Step 4 
<img width="853" height="109" alt="Screenshot 2026-02-23 at 5 19 44 PM" src="https://github.com/user-attachments/assets/1e0f71be-e7bf-4768-befa-7fab6f4b0e6b" />

- This command creates a place whre you can control the cluster.  Kuberetes creats a pod running curl image.  It is important because it tests service discovery from inside the cluster.  


### Step 5 

<img width="702" height="274" alt="Screenshot 2026-02-23 at 5 20 27 PM" src="https://github.com/user-attachments/assets/93329482-1c37-42d3-acfc-0fca37fa1221" />

- In this command, this is calliing to show what is running and exposed.  Kubernetes lists deployments, pods, and services.  It health checks and confirms labels.  In my picture, my pods say ImagePullBackOff, which tells me they are not running correctly,  I was able to eventually fix it, but not able to get a picture of it.  

### Step 6 

<img width="852" height="448" alt="Screenshot 2026-02-24 at 3 23 31 PM" src="https://github.com/user-attachments/assets/b416f826-9a61-45f2-a67b-96925b55303e" />


- These commands are very similar in that they are doing the same thing jsut for the proucts and orders which is where they differ.  Overall, they are call products via service DNS.  Kubernetes resolves products and orders to ClusterIP. 

## Task 3 
### Step 1 

<img width="844" height="35" alt="Screenshot 2026-02-24 at 3 24 16 PM" src="https://github.com/user-attachments/assets/b0640101-e25e-4bbf-947a-f1f7cefaab9f" />

- This command goes to orders source code because the could build needs the source context to build an image.  

### Step 2 

<img width="846" height="462" alt="Screenshot 2026-02-24 at 3 26 20 PM" src="https://github.com/user-attachments/assets/4a2d5422-fe12-486b-a718-52e9bb469af1" />


<img width="849" height="563" alt="Screenshot 2026-02-24 at 3 27 36 PM" src="https://github.com/user-attachments/assets/628a1db6-9d5b-4eb1-a607-53dd74787e8e" />

- In this command we use the cat server.js to confirm the file chnaged and catch any errors before building.  


### Step 3 

<img width="879" height="364" alt="Screenshot 2026-02-24 at 3 28 28 PM" src="https://github.com/user-attachments/assets/f500e367-6d09-4a70-924c-339b1eb6967b" />

- This command verifies your image exists and has tage v2, without it, the push would not have happened and the rollout will pull a missing image casuing the pods to fail.  

## Task 4 
### Step 1 
<img width="847" height="49" alt="Screenshot 2026-02-24 at 3 29 05 PM" src="https://github.com/user-attachments/assets/1e4bd29e-0714-4b35-8826-95189ebfe00d" />

- This command is trying to find what image is the orders deployment currently using.  Kubernetes returns the container image field in the pod template, allwoing you to confirm the baseline.  



### Step 2

<img width="851" height="44" alt="Screenshot 2026-02-23 at 5 38 38 PM" src="https://github.com/user-attachments/assets/37aad1f7-cd31-4277-b578-2145dd33e16b" />


<img width="854" height="80" alt="Screenshot 2026-02-24 at 3 29 37 PM" src="https://github.com/user-attachments/assets/a225d71b-2876-4c93-86b7-dcd6fbd99c2a" />

- The first command is to update the deployments pod template to use V2.  Kubernetes recieves the message to change the template and creats a new ReplicaSet, allowing the release a new verison without downtime.  The second command pauses the rolliut mid flight and kubernetes is stopping the scaling chnages.  It gives time to inspect a partial rollout.  


### Step 3 

<img width="860" height="181" alt="Screenshot 2026-02-24 at 3 30 02 PM" src="https://github.com/user-attachments/assets/e6ce28ea-8855-45ed-b25f-60d6cde43e7b" />

- This command allows you to watch the progress of rolling update and reports when desired replicas are updated.  Gives you a view to see if there are errors or if anything is failing.  

### Step 4 

<img width="867" height="195" alt="Screenshot 2026-02-24 at 3 31 00 PM" src="https://github.com/user-attachments/assets/d042a87f-c9bd-443a-a459-0b8369d90ef5" />

- This command taps the service repeatedly to see which version responds.  Kubernetes load balances across all matching pods.  

### Step 5 

<img width="839" height="74" alt="Screenshot 2026-02-24 at 3 31 23 PM" src="https://github.com/user-attachments/assets/34e412b5-d32e-41cd-802b-5bac5ec66b9f" />

- This commmand continues the rollout after we paused it earlier.  Kubernetes resumes shifting replicas until the rollout ends, overall finished the release.  

### Step 6 
<img width="853" height="98" alt="Screenshot 2026-02-24 at 3 40 52 PM" src="https://github.com/user-attachments/assets/2c7e7323-a21e-4e5e-b538-af7f373f8256" />

- This command rolls back to the previous deployment.  Kubernetes sets the deployment pod template back.  it is almost like a light switch to change from V2 to V1. 



### Step 7 
<img width="850" height="48" alt="Screenshot 2026-02-24 at 3 41 11 PM" src="https://github.com/user-attachments/assets/def196ca-7082-4174-b6bc-17fc4c08581c" />


<img width="845" height="106" alt="Screenshot 2026-02-24 at 3 41 35 PM" src="https://github.com/user-attachments/assets/fbb3ecc6-bb77-4c0c-8623-f7f13d99f5ac" />

- This first command shows the path for the my-repository.  This was apart of the problem I was having with the project as my-repository was in a previous lab and I made a new one for this lab.  In turn I went back an rebuilt my-repository for lab 4 and it ended up working.  The second command shows which image each pod is running.  It allows you to ensure before moving on.  

## Task 5 
### Step 1

<img width="858" height="47" alt="Screenshot 2026-02-24 at 3 42 18 PM" src="https://github.com/user-attachments/assets/db5ee30f-4445-474e-a0f8-71d2a7eb5d92" />

- Againa this command shows the path getting to my-repositry and how it is running on V1.  

### Step 2 
<img width="842" height="95" alt="Screenshot 2026-02-24 at 3 42 49 PM" src="https://github.com/user-attachments/assets/c6ed720f-ed98-4da1-8e56-22382baa777d" />

- This command prints working directory and shows where you are in your own system.  It is important because you want to know where you are in your machine.  ls is to list the files you are working with and as we can see all the .yaml files we have.  

 
### Step 4
<img width="855" height="171" alt="Screenshot 2026-02-24 at 3 44 11 PM" src="https://github.com/user-attachments/assets/cdbda9d7-f09f-4496-997f-fd8898800ece" />

- The second command creates a canary deployment running v2 alongside.  Kubernetes is another deployment with labels, the idea here is that you release a small bit of it to users first.  



### Step 5 
<img width="857" height="125" alt="Screenshot 2026-02-24 at 3 45 02 PM" src="https://github.com/user-attachments/assets/48639651-8772-4550-9296-b5c44b82b70e" />


- This command checks which pods are stable and which are canary.  It is important as canary relies on labels to distinguish versions.  

### Step 6 
<img width="851" height="212" alt="Screenshot 2026-02-24 at 3 45 31 PM" src="https://github.com/user-attachments/assets/448e5bd0-7cad-498e-9249-68353d264e05" />

- This command is simiilar to the rpvious, but also adds the IP adress of each one, allowing us to really see via labels.  

### Step 7 
<img width="851" height="81" alt="Screenshot 2026-02-24 at 3 45 59 PM" src="https://github.com/user-attachments/assets/eac53b8a-5ca3-4948-a52d-40bccf0cdf66" />

- This command sees the pods IP service.  EndPointSlice controller publishes endpoints for the service.  It confirms canary pods are included in servic routing. 


### Step 8 
<img width="852" height="133" alt="Screenshot 2026-02-24 at 3 46 24 PM" src="https://github.com/user-attachments/assets/0c9dda25-cfad-4af4-af77-4e7178cfa1ae" />

- This command asks to shows pod name and IP address, track label, and the container image.  



### Step 9 
<img width="850" height="256" alt="Screenshot 2026-02-24 at 3 47 43 PM" src="https://github.com/user-attachments/assets/d71c05ed-37b5-49f0-8327-c25e925e4af3" />

- This command is sending repeated requests to obersve mixed routing.  It demonstrates traffic splitting through the shared service selector.  




### Step 10 
<img width="858" height="210" alt="Screenshot 2026-02-24 at 3 48 33 PM" src="https://github.com/user-attachments/assets/0a4b8a88-f807-4101-8dbd-03c207261045" />

- This first command deletes canary, to terminate the pods.  Gives a clean rollback of the canary so we can move on to the next idea.  The second command calls the pods to confirm to us they deleted.  



## Task 6 
<img width="800" height="140" alt="Screenshot 2026-02-24 at 3 49 57 PM" src="https://github.com/user-attachments/assets/f69142ec-7655-4afa-9a82-26707b840e44" />

- This command acts a quick check to ensure you are running the correct pods and that they are healthy.  

### Step 1 
<img width="852" height="181" alt="Screenshot 2026-02-24 at 4 00 09 PM" src="https://github.com/user-attachments/assets/7d95a4c5-05c5-4340-a119-f897780997dc" />

- This commmand calls into the pods to call from within the pods to ensure that the request reached it and is repsonding appropriately.  


### Step 2 

<img width="867" height="439" alt="Screenshot 2026-02-24 at 4 01 12 PM" src="https://github.com/user-attachments/assets/6281c6d4-bb3c-4caf-978a-001ec801c437" />

- The first command in this to label the deployment pods as blue, this chnages the pod template and triggers new rollouts.  The blue/green labels help direct the traffic.  The second command forces new pods, kubernetes deploys a template to trigger ReplicaSet, all of this ensures the pods get the new label.  


### Step 3 
<img width="846" height="455" alt="Screenshot 2026-02-24 at 4 02 11 PM" src="https://github.com/user-attachments/assets/ffb14142-4dc8-498c-97e1-2ab3e5b723ff" />

- This command is shwoing all the orders pods and telling which track eahc image is running.  Kubernetes filters pods with label app=orders.  The second command is to only send traffic to pods labeled app = orders and track = blue.  Kubernetes updates the service selector and kubernetes recalculates which pods match.  The third command shows exaclty what selector the service is using.  The last command is to hit orders-service 10 times and print the HTTP status code.   

### Step 4 
<img width="853" height="556" alt="Screenshot 2026-02-24 at 4 04 17 PM" src="https://github.com/user-attachments/assets/046e1b0b-6e15-4d78-abd3-0fbe352ce397" />

- This command is creating a brand  new Kubernetes deployment manifest for the green environment.  When applied it cretaes a second set of orders that can exists side by side.  The second command creates this green deployment in Kubernetes.  This shows now you have green pods running.  The third command is to wait until green is fully healtyh and running.  Kubernetes checks on replicas, the pods, and rollouts.  

### Step 5 
<img width="845" height="182" alt="Screenshot 2026-02-24 at 4 05 54 PM" src="https://github.com/user-attachments/assets/17042e9e-c530-46d4-816a-2cbbef5b0c71" />

- This command lists all the pods with label app=orders and print sout pod name, track label and contianer image version.  


### Step 6 
<img width="848" height="181" alt="Screenshot 2026-02-24 at 4 06 22 PM" src="https://github.com/user-attachments/assets/bce17926-d40b-4697-b3a4-24e765dc95ec" />

- This commmand runs inside http-client pod.  Kubernetes asks the node running http-clientto start a process inside to output what is going on inside.  This is the testing of the network from inside the cluster.  

### Step 7 
<img width="844" height="89" alt="Screenshot 2026-02-24 at 4 06 56 PM" src="https://github.com/user-attachments/assets/67205f53-4b56-40a2-b86d-fd9520f3b2ca" />


- The first command in this is the traffic switch from the blue to green.  Kubernetes is updating the service object and recomputing the EndpointSlice for the pods to match the selector.  Showing both versions cna be running at the same time, which shows how easy it is to run back and forth between blue and green.  The second command shows which labels the service is using to pick pods.  


### Step 8 
<img width="846" height="228" alt="Screenshot 2026-02-24 at 4 07 37 PM" src="https://github.com/user-attachments/assets/6efb0d3d-d2f7-4a5d-92c4-6f9b81b1cb3f" />

- This is simialr to the one we ran before to call from inside the cluster to confirm it responds successfully.  Kubernetes DNS resolves orders-service to service ClusterIP.  The second command it to show which versions actually responded to the call.  

### Step 9 
<img width="838" height="272" alt="Screenshot 2026-02-24 at 4 08 09 PM" src="https://github.com/user-attachments/assets/57ffe785-d322-4a17-bdf7-65b6eec66a97" />

- This first command calls from isndie the lcuster to askk what service version.  Kubernetes routes the request through the service to which pods match the service selector.  The second command is the switch to stop sending traffic to green and switch to the blue track.  The third command verifies the service still works after the switch.  

### Step 10 


<img width="859" height="91" alt="Screenshot 2026-02-24 at 4 08 52 PM" src="https://github.com/user-attachments/assets/298ebb20-4a90-4db9-9a39-932362e431d3" />

- This command lists all the pods and shows their names, whether they are blue or green, and what contianer image they are running.  Kubernetes returns all pods labeled with app = orders.  

## Task 7 (Reflection Questions) 

1.) A dark launch is when a new version of a service is deployed and fully running in production, with no real user traffic.  It gives oppurutnity to test it internally.  This is differnt from canary because canary uses a small percentage of real user traffic to test.  It is different from blue-green as blue green is two distinct environment being switch on and off.  Advanatges of dark launch is it can be observed in rela time, engineers can do different kinds of testing, and takes out the risk of bugs or errors to actual users.  In turn it also requires extra resources and can increae complexity across two different systems.  Engineers may choose dakr launch for for major changes that may be risky or complex.  
2.) Rolling updates reduce downtime, but dor not get rid of it completely.  You can still encounter downtime if the new version fails, limited resources, and the new pods are not ready in time.  The assumptions that must be true is that old and new versions must be compatible, databases schemas should not break older pods, and configuration changes must not invaliadate older versions.  Rolling updates are preffered with horizontally scalabe systems and high availability API's.  
3.) Limiting traffic reduce risks by only allowing a small subset of users to fail. Engineers can detect problems early.  Monitoring is required because canary requires observability with error rates, latency metrics, and memory usage.  Some disadvantages would be increasing complexity, strong monitoring capabilities, and sometimes bugs may only appear under a full traffic load.   
4.) Instant rollback is possible with blue-green deployment because the ability to have two full environments to exist at the same time, rollback is really just witching from environment to environment.  This increases infrastructure cost as you need the blue and green environment to run at the same time, doubling resources.  It is safer for a hard cutover when the new version is not backward compatible, major architecture changes, and consistency across all users at once.  It is often used for database schema chnages as schema changes can break older versions.  Blue-green allows a fully compatible new environment, validating it, and switching traffic only when it is ready.  
5.) A/B testing is for experimentaing, not deployment.  It is used to compare two variations of a feature to measure user behaivor and which version performs better.  Used for UI design, feature variations, or pricing changes.  It is not used for bug fixes as it is not meant for stability or safety.  It is to measure user response.  it is focused on optimizing product outcomes.  

## Task 8 
<img width="838" height="156" alt="Screenshot 2026-02-24 at 4 14 27 PM" src="https://github.com/user-attachments/assets/4af23146-2757-45d7-8590-30855831002e" />

- This command is the cleanup to delete your gke-cluster.  This is important to ensure you do not have pods in your cluster continuously running.  

