# Update and delete from database

![](../images/update-from-db-1.png)


## AIM

The AIM of the following paragraphs is to learn how to update and delete data from base in your scripts with queries to DB. 

The steps involved will include:

1.	Open our last project.
2.	Updating memory data
3.	Add journaling system
4.	Challenge exercise


Estimated Completion Time: 46 minutes 

![](../images/update-from-db-2.png)

**Step 1 :** Open our last project – calulatop.py in IDE that you love. The good idea is look through the code we have. What functionality we have? What we need to do one more? 
We have 4 binary operations - *,/,+,-
And 2 unary operations ++,--
And 2 like unary operations – unary + and –(they like binary, but add and subtract number with oneself.
 2 memory methods – get and save.

**Step 2 :** Now look at last homework that we have. For this time we mast already have method get()from DB value that we save with save method.

![](../images/update-from-db-3.png)

And here is explanation of get() method:

![](../images/update-from-db-4.png)

Here we simply get value with _idkey from dbvalue. But what we get if we start program and want to call method get()at first? We get TypeError, because we try to get from None object value withkey value.

![](../images/update-from-db-5.png)

**Step 3 :** Now we rewrite function get() to right way. We can’t create hard logic to see if there is an object with _id that we want and if that object have value. Or simply check – if our search return not None object.

![](../images/update-from-db-6.png)

Task completed

![](../images/update-from-db-7.png)

**Step 1**. Now we must correctly rewrite method save and get. At first we move up initialize index variable and then rewrite insert method to update in seve() function and move up initialize index variable.

![](../images/update-from-db-8.png)

Here we at each start of program cleaning db to removeside effect of our program. That mean that if we only start program we haven’t any save data and get() function nothing return.

**Step 2** Now rewrite function save()

![](../images/update-from-db-9.png)

Task Completed

![](../images/update-from-db-10.png)

**Step 1** Last practice for today is write journaling system. Which save all our activity.
At first we create function journaling() and curr_journallvariable.

![](../images/update-from-db-11.png)

Now add some logic for function. Create new documents data base in existing data base in function connection().

![](../images/update-from-db-12.png)

**Step 2** Now we have new DB. And we must enter here all our activity.
Inserting we have only in function journal. And we creating data to inserting in each function with work with our input data. So adding create string inserted to DB.

a)	At first do it when we enter to our program.

![](../images/update-from-db-13.png)

b)	Now create journal message in function save 

![](../images/update-from-db-14.png)

c)	and get data from DB.

![](../images/update-from-db-15.png)

d)	And in our logic operations (binary).

![](../images/update-from-db-16.png)

e)	And unary

![](../images/update-from-db-17.png)

![](../images/update-from-db-18.png)

**Step 3** Now update our function journaling()to save our curr_journal.

![](../images/update-from-db-19.png)

As you see, now we delete including global variables sum and operand. Because all data that we must save, already existing in curr_journalvariable.

Task completed

Challenge exercise:
Add to program in Listening #3 possibility see all journal or some count message from journal DB.


