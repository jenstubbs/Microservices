## Phase 2, Hands on submission
### Google CloudLab: Building Change Data Capture usnig Dataproc and Cloud Pub/Sub

The Purpose of this lab was to build and end to end change data capture pipeline.  Each task in the lab represents a component of a real time data piepline architecture.  First Pub/Sub was configured to act as the messagig system for stremaing data base change events.  A python script then simulated database changes and published the events to Pub/Sub to represent a data producer.  A service account was created to allow secure communicaiton between services.  A dataproc clsuter was then created to provide a dsitributed spark processing environment.  Lastly, a sprak streaming job was submitted to consume messages from Pub/Sub and process them in real tim.  These events all tie together as they demonstrate event drien dtaa pipelins capture, strema,a nd process data changes in cloud architecture.  

### Introduction (Task 1)
#### Step 1 
<img width="799" height="77" alt="Screenshot 2026-03-31 at 5 20 36 PM" src="https://github.com/user-attachments/assets/e4cdbcd5-4eea-4890-b474-4a8ba8a6049b" />

- In this task, we use a command to enable the required API's, which are Dataproc anc Pubsub.  This is imporatant as API's are needed to create clusters, send messages, and run spark jobs.  Without these API's the clod components would not be able to communicate.  
### Task 2
#### Create a Topic 
<img width="737" height="36" alt="Screenshot 2026-03-31 at 5 21 05 PM" src="https://github.com/user-attachments/assets/7e7e9dd2-4565-41b2-be52-1c1dd6b17326" />

#### Cretae a Subscription
<img width="917" height="48" alt="Screenshot 2026-03-31 at 5 21 29 PM" src="https://github.com/user-attachments/assets/2e32236f-2f9b-498c-a536-288992420dac" />

- In this task we created a topic and subscription.  In Pub/Sub, it is like a messaging system and the topic part processing messages and pointing them where they need to go.  The subscription piece is in charge of who recieves the messages.  This is the event streaming layer of the pipeline.  Instead of changes going directly to Dataproc, they go to Pub/Sub and this makes the system scalable, event driven, and decoupled.   

### Task 3

In this task overall I ran a python script that generated events such as insert, update, and delete.  In a real system databases constantly change, CDC pipeline captures the changes, and the chnages then become events.  Since there is no real database connected, this script allows us to simulate the change data capture events and publishes them as messages.  This is the data producer example in the system.  
#### Step 1 
<img width="795" height="491" alt="Screenshot 2026-03-31 at 5 35 38 PM" src="https://github.com/user-attachments/assets/e907163f-8dc2-4f7e-9dae-6914ce125dcb" />

- In this step, i created a python script to simulate database changes and publish them to Pub/Sub.  

#### Step 2 
<img width="915" height="289" alt="Screenshot 2026-03-31 at 5 34 50 PM" src="https://github.com/user-attachments/assets/5b08a790-484e-4e91-89ad-a357590382e0" />

- This step in installing the Pub/Sub client library

#### Step 3 
<img width="636" height="198" alt="Screenshot 2026-03-31 at 5 32 13 PM" src="https://github.com/user-attachments/assets/c4d2a88f-1539-4609-9d63-39f3e1398b0b" />

- In this step, we run the script in the terminal and the script runs continuously and publishes message to the Pub/Sub topic.  
#### Step 4
<img width="621" height="180" alt="Screenshot 2026-03-31 at 5 37 14 PM" src="https://github.com/user-attachments/assets/bd3dd587-a14e-49e6-a714-3f4d8bd4952c" />

- This step shows the stopping of the script as we needed just enough messages to consume.  If i did not stop this, it would just continuosuly run.  

#### Step 5 
<img width="914" height="121" alt="Screenshot 2026-03-31 at 5 32 45 PM" src="https://github.com/user-attachments/assets/8a7f9ab9-58d7-4a7e-9316-37035e03110a" />

- In this step we opened another terminal to see the published messages.  You can see the table row with the message {"change_type":"UPDATE"...}

### Task 4 

In this task overall, we are creating a service account and giving it roles.  Dataproc needs permission to read from Pub/SUb, run jobs, and access cloud resources.  This Task is focusing on security, authenticaiton, and authorization.  This is important as cloud systems use IAM roles to control service communication.  
#### Step 1
<img width="841" height="62" alt="Screenshot 2026-03-31 at 5 37 46 PM" src="https://github.com/user-attachments/assets/595737e5-d4d3-43fc-b761-48811f619616" />

- In this step, we create a service account.
#### Step 2 
<img width="886" height="430" alt="Screenshot 2026-03-31 at 5 42 13 PM" src="https://github.com/user-attachments/assets/fdd199c4-0def-4bf1-85eb-f4c0f949bda8" />

- In this step, the Dataproc worker role is added to allow the service account to create clusters and run jobs.  
#### Step 3

<img width="824" height="467" alt="Screenshot 2026-03-31 at 5 42 44 PM" src="https://github.com/user-attachments/assets/49d6bd7f-ec07-447d-8abb-d6980b4748f1" />

- This step adds the Pub/Sub subscriber role to allow the service account to subscribe to the "change-subscriber" subscription.  

### Task 5

In this task, the objective was to create a Dataproc cluster, a big cluster meant for processing big data.  We remeber that Pub/Sub only stores messages, but we need somethign to process the data stream.  Dataproc and Spark work together and stream process and data transformation.  This step is like the processnig enging of the pipeline.  There are two screenshots attached to this task as I ran into many hours and of trying to create clusters in just about every region, with it telling me there was not enough resources available.  With lots of troubleshooting I was able to  mkae the cluster.  I did have to mchaneg the region I was in and make the cluster smaller.  With that, the rest of the lab still worked the same.  
#### Step 1 
<img width="909" height="401" alt="Screenshot 2026-03-31 at 5 50 13 PM" src="https://github.com/user-attachments/assets/a3dc79e4-b935-4030-85dc-4e815c742676" />

<img width="912" height="337" alt="Screenshot 2026-03-31 at 10 19 54 PM" src="https://github.com/user-attachments/assets/b5ade181-b412-4755-a273-ce6a37b97ac2" />

- This step creates the clusters which will run the spark app which will process the messages in the Pub/Sub.  

#### Task 6

This task was the longest task of all the task.  As in this task I submitted a spark stremaing job that, read messages from Pub/Sub, processed them, and printed the results.  This step is essentially the connection of the pipelin that was built in the lab.  So now the system is following the order of Database changes, events sent to Pub/Sub, Dataproc reads event, and Spark processes event in real time.  This is the consumer and processing layer.  
#### Step 1
<img width="905" height="46" alt="Screenshot 2026-03-31 at 10 21 36 PM" src="https://github.com/user-attachments/assets/d5c38b0c-652e-4d5f-8bab-d9a1936881e1" />

<img width="913" height="35" alt="Screenshot 2026-03-31 at 10 25 27 PM" src="https://github.com/user-attachments/assets/21bb53a4-2e0f-45a7-a99a-fdb8fcaa14a4" />

- In this step, I created a directory and added the source code of the consumer to the file.  I did not show the full source code, but in my screenshots you can see the making of the directory command and the opnening nano command in order to pub the source code in. I did not include the soruce code as it was long.   
#### Step 2
<img width="770" height="35" alt="Screenshot 2026-03-31 at 10 27 30 PM" src="https://github.com/user-attachments/assets/6214ac66-0f1e-4ed5-89e7-8f787bf42d5a" />

- Simialr to the last step, I created and added source code to pom.xml.  I included the screenshots of reaching the pom.xml and the nano command to open the file.  The source code was quite long and that is why I did not include it.  


#### Step 3 
<img width="785" height="47" alt="Screenshot 2026-03-31 at 10 27 57 PM" src="https://github.com/user-attachments/assets/7f5daf03-52fb-4793-a696-16ff55f9d5b3" />

- In this step, I changed the projects sprak directory and save the path in an environemnt variable.  

#### Step 4 
<img width="840" height="49" alt="Screenshot 2026-03-31 at 10 39 11 PM" src="https://github.com/user-attachments/assets/2595f468-0f19-4721-8c82-ffc450c6680d" />

- This step chnaged the directory.  

#### Step 5 

<img width="903" height="532" alt="Screenshot 2026-03-31 at 10 39 55 PM" src="https://github.com/user-attachments/assets/9ce40589-f772-4ca1-9cd7-06c15fa2927d" />


<img width="714" height="93" alt="Screenshot 2026-03-31 at 10 40 24 PM" src="https://github.com/user-attachments/assets/c0dcedfa-224e-41a5-a9f2-9950d9220c11" />

- This step, I needed to download the Java 1.8.  Google cloud keeps up with updated version of Java and It was using Java 11.  So I had to do a few extra steps in order to get Java 1.8.
#### Step 6 

<img width="914" height="187" alt="Screenshot 2026-03-31 at 10 41 08 PM" src="https://github.com/user-attachments/assets/9a721e59-5af7-4e0d-93c3-e2a4f76ac8b5" />

- Thi step build the application Jar, we can see with the build success, that it worked.  

#### Step 7
<img width="927" height="545" alt="Screenshot 2026-03-31 at 10 42 40 PM" src="https://github.com/user-attachments/assets/ace2f4dd-edd9-4541-8caa-97726baf364c" />

- This task is submitting the spark application.  

#### Step 8 
<img width="913" height="78" alt="Screenshot 2026-03-31 at 10 44 14 PM" src="https://github.com/user-attachments/assets/b3252e12-3526-4110-9a41-ce564965b79a" />

- This step will display the list of active jobs and the labe told me to take special note of the JOB_ID value.  We can also see the type which is spark and that it was up and running.  

#### Step 9 

<img width="924" height="874" alt="Screenshot 2026-03-31 at 10 51 00 PM" src="https://github.com/user-attachments/assets/6dd8a3b3-f6a7-4605-98a9-17a48996c254" />

- This step, the lab gave a URL, with your own JOB_ID included in it.  This then took you to a page where you could see in real time the system looking for messages and the messages being recieved 
#### Step 10 
<img width="657" height="190" alt="Screenshot 2026-03-31 at 10 50 25 PM" src="https://github.com/user-attachments/assets/ba4ccd4a-a3a3-444d-ac8d-67a0f5d1db33" />

- This is part of the previosu step as when we put the URL in to the browser we were able to see the system looking for messsages and messages being recieved.  I did have issues at this part as initially it was only looking for messages and not finding any, but I did leave my computer for around an hour at that point and had to go in and reactivate my python script from earlier.  This instantly changed what I was seeing and was getting message recieved instead of just the looking for messages.  
#### Step 11 
<img width="913" height="140" alt="Screenshot 2026-03-31 at 10 52 25 PM" src="https://github.com/user-attachments/assets/ac81b8da-bf46-4272-9175-25215fac0cee" />

<img width="908" height="139" alt="Screenshot 2026-03-31 at 10 53 48 PM" src="https://github.com/user-attachments/assets/e22d378c-cd4e-46fe-9352-ccc28b39033a" />

- This step terminated the job otherwise it would have just been continuously running in the background.  
### Task 7 (Clean-up)
#### Step 1 

<img width="919" height="213" alt="Screenshot 2026-03-31 at 10 57 16 PM" src="https://github.com/user-attachments/assets/1b34e8ed-1b67-4129-a265-47c79c0ecc69" />

- This task was the clean up task.  As we do in our labs in class, we must go back in and delete the the resources we made to not be billed in the future.  









