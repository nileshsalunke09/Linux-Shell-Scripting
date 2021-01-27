# **Linux-Shell-Scripting.**

# **Chapter 3: Shells (bash) structured Language Constructs.**

- Decision making
- Loops

Is there any difference making decision in Real life and with Computers? Well real life decision are quite
complicated to all of us and computers even don't have that much power to understand our real life
decisions. What computer know is 0 (zero) and 1 that is Yes or No. To make this idea clear, lets play
some game (WOW!) with bc - Linux calculator program.

### #bc

After this command bc is started and waiting for your commands, i.e. give it some calculation as follows

type 5 + 2 as:

5 + 2

7

7 is response of bc i.e. addition of 5 + 2 you can even try

5 - 2

5 / 2

See what happened if you type 5 > 2 as follows

5 > 2

1

1 (One?) is response of bc, How? bc compare 5 with 2 as, Is 5 is greater then 2, (If I ask same question to you, your answer will be YES), bc gives this 'YES' answer by showing 1 value. Now try

5 < 2

0

0 (Zero) indicates the false i.e. Is 5 is less than 2?, Your answer will be no which is indicated by bc by showing 0 (Zero). Remember in bc, relational expression always returns true (1) or false (0 - zero).


It means when ever there is any type of comparison in Linux Shell It gives only two answer one is YES and NO is other.

Linux shell value = Zero(0) = Yes/True

Linux shell value = Non-Zero = No/False

# **if condition**

if condition which is used for decision making in shell script, If given condition is true then command1 is executed.

	if condition
	then
		command1 if condition is true or if exit status
		of condition is 0 (Zero)
	fi..



Condition is defined as:
"Condition is nothing but comparison between two values."

For compression you can use test or [ expr ] statements or even exist status can be also used.

Expression is defined as:
"An expression is nothing but combination of values, relational operator (such as >,<, <> etc) and
mathematical operators (such as +, -, / etc )."

Following are all examples of expression:

5 > 2

3 + 6

3 * 65

a < b

c > 5

c > 5 + 30 -1

Write shell script as:

![Screen Shot 2021-01-27 at 11.57.35 PM.png]({{site.baseurl}}/Screen Shot 2021-01-27 at 11.57.35 PM.png)

Run above script as:
![Screen Shot 2021-01-28 at 12.00.40 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.00.40 AM.png)



    
 








