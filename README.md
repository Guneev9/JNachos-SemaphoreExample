# JNachos-SemaphoreExample
Implementation of Synchronization program to generate Hydrogen Peroxide molecules(H2O2)

There are the following 5 semaphores:
1)H
2)O
3)Wait
4)Mutex
5)mutex1

1) H Semaphore–
It will make the first Hatom to sleep until the second one comes and then it wakes it up.The count for this semaphore is 0, which means that it will block the first thread, and any following threads, which is calling calls P() on it. It is set as 0 as, we want to stop the first Hatom from progressing in execution until we get ahold of the second Hatom.

b) O Semaphore-
It will make the first Oatom to sleep till the second Hatom will wake it up. Once the Oatom is awake, it knows it has all the resources necessary to create water. The count for this is 0, which means that it will block the first, and any following, Oatom threads that calls P() on Semaphore O. it is set to 0 is because we want to pause execution until we have both Hydrogen atoms ready. Once we have access to both Hydrogen atoms, the latter of the two Hydrogen atoms wakes up the Oxygen atom and
the Oxygen atom proceeds to creating water.

c) Wait Semaphore-
It will set the Hatoms to sleep till, water has been created and prints the message. Once it is completed, the two Hatoms are  then woken up and finish executing. It is also set as 0, thus it will block the first, and any following, thread that calls P() on this semaphore. It is set to 0 since we want to stop all Hatoms from proceeding further in their execution until after the Oatom has created water and will print the message.Once this is done, the Oxygen atom wakes up the corresponding Hydrogen atoms and these processes now finish executing.

d) Mutex Semaphore-
It will to make sure that there is only one thread in the Hydrogen critical section at a time.The critical section in the Hatom class in call function is the block. In this, conditional block, I am checking the count. Statements inside if and the else sections of the block, incrementing the count, are inside the critical region. The second line increments the
counter in the mutex, of the if and else part of the block, then, it is outside the critical section.

e) Mutex1 -
It will make sure that there is only one thread at a time in the critical section of Oxygen at a time.Critical section in the Oatom class for the call() is the set of statements after the makeWater() function, including it as well. These statements decrements count of recent Hatom, decrements the recent Oatom count, and then prints. This whole section is kept safe by its own mutex.

Hatom Logic:

a)It has one variable(mid) which has the id of Hatom and one constructor and one function.

b)The constructor is initializing mid with Hatom id

c)The multi-threading is done by call function. The very first statement in it is calling P() on the mutex semaphore in order to so make sure that only one thread is there inside the critical section at a time.

d)Once we enter the critical section, we have an if statement which checks, the count (which has a track of the number of Hatoms, initially set to 0. If the count is even, then it’s the first Hatom for its making water, or else if the count is odd then it's the second hydrogen that will be used in the water making.

e)When the count is even, I have incremented the count and the critical section is ended by invoking V() on mutex.

f)After that, current Hydrogen thread is set to sleep by invoking P() on it, because doing so, that i can wait for the 2nd Hatom to wake us up.

g)When the count is odd, I have increment the count and critical section is ended by calling V() on mutex semaphore.

h)Then the first Hatom is made to wake up and which has to create the formula. By now, both the Hatoms are available to move ahead in execution till they reach the wait,Then call P() on it, and both atoms will go to sleep till the Oatom makes the water or the Oatom increments wait before the Hatoms get to the wait semaphore, so that they will not go to sleep.

i)Once they get through the wait semaphore, they will print their id values and exit.

Oatom Logic:
It has one variable(mid) which has the id of Oatom and one constructor and one function.

a)The constructor initializes the id of Oatom to value passed in as an argument(mid). 

b)The multi-threading is done by call function. The very first statement in it is

c)calling P() on the Oatom because, I don’t want to continue the execution till I have the idea that whether both the Hatoms resources are ready. 

d)The 2nd Hatom is also taking care of waking up the Oatom, so that i will be able to make water when the Oatom wakes up, as i know that i have access to both Hatoms. 

e)As the Oatom has started its execution again, it will prints a message (making water) and then wakes up the two sleeping Hatoms which will wait for the message to print so that they will finish execution, then will update the current Hatom and Oatom counts, 

f)Then, it prints the count value, and will end the critical section by incrementing its mutex.

g)It will then print ids of atoms.

Implementtion:
As I have explained the functioning of Hatoms and Oatoms above, so here, I have referred to the existing Water.java file for this question. I have not made any changes to Hatom because here also it requires 2 atoms for completion. I have only modified the code for Oxygen atoms.
In water.java for water, it will need single Oatom and wake it up once the Hydrogen resources are safe. Here, also same approached is used.The only change is we need 2 Oatoms to sleep till Hatoms are made and thus, making the
formula.
