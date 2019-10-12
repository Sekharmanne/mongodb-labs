# Replica Set Deployment - Part 1

![](../images/replica-set-deployment-1.png)

## AIM

The AIM of the following exercise

The steps involved will include:

1. Launching replica set
1.	Configuring replica set
2.	Mongo web interface
3.	Reatd and write operations

Estimated Completion Time: 40 minutes 

![](../images/replica-set-deployment-2.png)

Launching and configuring replica set

**Step 1.**  Before launching a replica set, create folders to store member’s data:

a)	Navigate to the “C:\MongoDB\dbs” and create subdirectory ”rs_test”. 

![](../images/replica-set-deployment-3.png)

b)	Then create three new subdirectories inside that, you just created:

![](../images/replica-set-deployment-4.png)

Each folder will contain contain one of the members. 

c)	Three new ones will be found in your folder C:\MongoDB\dbs\rs_test:

![](../images/replica-set-deployment-5.png)

**Step 2.**  Open three cmd windows and create three new instances of mongodb servercontemporaneously in these windows: 

mongod --port 27017 --replSet test --dbpath C:\MongoDB\test_rs\rs1 --rest
mongod --port 27018 --replSet test --dbpath C:\MongoDB\test_rs\rs2 --rest
mongod --port 27019 --replSet test --dbpath C:\MongoDB\test_rs\rs3 –rest

The commands above include the following properties:
•	portanddbpath – similar from previous chapters
•	replSet - unique name for replica set which is given to all members
•	rest - to enable rest interface for the admin web page

![](../images/replica-set-deployment-6.png) put configuration image

**Step 3.** Now, let’s configure our replica set.

a)	Create new cmd window and connect to server rs1 using mongodb shell:

![](../images/replica-set-deployment-7.png)

b)	Next, the replication set must be initialized. To initiate the replica set, create the config and carry out the following command:

![](../images/replica-set-deployment-8.png)
 
You can enter the rs.status () in the shell prompt to check how many servers are in the replica set.

![](../images/replica-set-deployment-9.png)

As you can see we have only one server added to replica set, which is primary now. 

c)	Let's add the rest of the servers to the replica set:

![](../images/replica-set-deployment-10.png)

d)	And look at the status again:

![](../images/replica-set-deployment-11.png)

![](../images/replica-set-deployment-12.png) 

We have one primary and two secondary members.

**Step 4.**  Replication web interface. As we have used –rest option at the launch of replica set members, mongodb provides web interface to our replica set.

The following URL should be entered to the browser address bar: 
http://<machine-name>:<port>/_replSet 

Our url seems like:
http://localhost:28017/_replSet
Port 28017 is used by default.

![](../images/replica-set-deployment-13.png) 

![](../images/replica-set-deployment-14.png)
Picture 10.1.1Replication web interface

There is ability to view replica set config, get replica set status, see docs and other.

![](../images/replica-set-deployment-15.png)

**Step 5.**  Read and write to replica set.

a)	Launch new console and connect to the secondary port (27018 or 27019)

The output string tells us that we are connected to secondary member.

![](../images/replica-set-deployment-16.png) main image

b)	Switch to the console with primary member and save documents:

![](../images/replica-set-deployment-17.png)

**Step 6.**  Now, let’s try to get these books from the secondary member.

a)	Firstly the following command should be executed:

![](../images/replica-set-deployment-18.png)

By default, the reading from secondary members is prohibited. This is to protect you from performing eventually consistent reads by accident. The command above permits the reading 

b)	Find all books

![](../images/replica-set-deployment-19.png)

Replica set work correctly.


