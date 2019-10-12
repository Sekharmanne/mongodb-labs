# Working with PyMongo - Part 2

![](../images/working-with-pymango-1.png)

## AIM

The AIM of the following exercise

The steps involved will include:

1. Connectig to the mongodb
2. Read and write operations
3. Read preferences
4. Replica set member tagging
5. Fault tolerance in motion


Estimated Completion Time: 30 minutes 

![](../images/working-with-pymango-2.png)

PyMongo makes working with replica sets easy.

**Step1.** To connect to the running replica set (from previous lab work)

a)	import pyMongo:

![](../images/working-with-pymango-3.png)

b)	There are few different ways to connect to the replica set:

![](../images/working-with-pymango-4.png)
 
As you can notice, the result is the same. So take you pick and save connection to variable:

![](../images/working-with-pymango-5.png)

**Step 2.** To ensure the correctness of connection:

a)	output book collection from the previous lab:

![](../images/working-with-pymango-6.png)

b)	And try to save some book:

![](../images/working-with-pymango-8.png)
 
c)	Open new mongo console, and verify that the new book was saved successfully.

![](../images/working-with-pymango-7.png)

![](../images/working-with-pymango-9.png) 

**Step 3.** Instead of a simple MongoClient you can use MongoReplicaSetClient. It offers two key features: secondary reads and replica set health monitoring. 

a)	To connect using MongoReplicaSetClient just provide a host: port pair and the name of the replica set:

![](../images/working-with-pymango-10.png)

b)	You can change read preference. It means that you recommend pymongo some replica member to perform operations.

![](../images/working-with-pymango-11.png)

![](../images/working-with-pymango-12.png) 

**Step 4.** One of the pymongo features is the selecting member according to tags.

a)	Switch to mongo and reconfigure the replica set

![](../images/working-with-pymango-13.png)

We added tags which describe the location of the member.

b)	Now, we may choose member with a region. Set read preference to “Secondary” and passthe appropriate tags:

![](../images/working-with-pymango-14.png)

c)	And test the connection:

![](../images/working-with-pymango-15.png)


**Step 5.** If something bad has occurred with primary member, pymongo automatically reconnects to the new primary member

a)	Reconnect to the replica set with the simple connection and check out connection port:

![](../images/working-with-pymango-16.png)

![](../images/working-with-pymango-17.png)

If the combination “<Ctrl>+<C>” is pressed in our mongod instance with primary member, the process ends. So that, switch to the console with primary member and press “<Ctrl>+<C>”.

b)	When we will try to read something, an exception will be thrown.

![](../images/working-with-pymango-18.png)

On subsequent attempts to run the query we might continue to see this exception. 

![](../images/working-with-pymango-19.png)

c)	Eventually, replica set will elect a new primary

![](../images/working-with-pymango-20.png)

The new primary member is running on the 27018 port.




