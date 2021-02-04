# **Linux-Shell-Scripting.**

# **Chapter 3: Shells (bash) structured Language Constructs.**

- Decision making
- Loops

Is there any difference making decision in Real life and with Computers? Well real life decision are quite
complicated to all of us and computers even don't have that much power to understand our real life
decisions. What computer know is 0 (zero) and 1 that is Yes or No. To make this idea clear, lets checkout with bc - Linux calculator program.

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

- # **if condition**

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

Shell script name is showfile ($0) and nilesh is argument (which is $1).Then shell compare it as follows:

if cat $1 which is expanded to if cat foo.

### **Exercise**

Write shell script as follows:

![Screen Shot 2021-01-28 at 12.06.32 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.06.32 AM.png)

Run above script as:

![Screen Shot 2021-01-28 at 12.07.17 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.07.17 AM.png)

### **Answer the following question in referance to above script:**

(A) foo file exists on your disk and you give command, $ ./rmfi foo what will be output?

(B) If bar file not present on your disk and you give command, $ ./rmfi bar what will be output?

(C) And if you type $ ./rmfi What will be output?


#### **Answers**

(A)

![Screen Shot 2021-01-28 at 12.09.01 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.09.01 AM.png)

(B)

![Screen Shot 2021-01-28 at 12.09.40 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.09.40 AM.png)

(C)

![Screen Shot 2021-01-28 at 12.10.55 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.10.55 AM.png)


- # **test command or [ expr ]**

test command or [ expr ] is used to see if an expression is true, and if it is true it return zero(0), otherwise returns nonzero for false.

Syntax:
test expression OR [ expression ]

### **Following script determine whether given argument number is positive.**

![Screen Shot 2021-01-28 at 12.17.17 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.17.17 AM.png)

Run it as follows:

![Screen Shot 2021-01-28 at 12.21.19 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.21.19 AM.png)

- Detailed explanation
The line, if test $1 -gt 0 , test to see if first command line argument($1) is greater than 0. If it is true(0) then test will return 0 and output will printed as 5 number is positive but for -45 argument there is no output because our condition is not true(0) (no -45 is not greater than 0) hence echo statement is skipped.
And for last statement we have not supplied any argument hence error ./ispostive: test: -gt: unary
operator expected, is generated by shell , to avoid such error we can test whether command line argument is supplied or not.

- test or [ expr ] works with

1.Integer ( Number without decimal point)

2.File types

3.Character strings

### **NOTE: == is equal, != is not equal.**

-eq = is equal to. 

-ne = is not equal to.

-lt = is less than.

-le = is less than or equal to.

-gt = greater than

-ge = is greater than or equal to.


string1 = string2 = string1 is equal to string2

string != string2 = string1 is NOT equal to string2

string1           = string1 is NOT NULL or not defined 

-n string1        = string1 is NOT NULL and does exist

-z string1        = string1 is NULL and does exist


! expression      = Logical NOT

expression1 -a expression2 = Logical AND

expression1 -o expression2 = Logical OR

- # **if...else...fi**

If given condition is true then command1 is executed otherwise command2 is executed.

Syntax:

	if condition
    then
    	condition is zero (true - 0)
        execute all commands upto else statement
	else
    	if condition is not true then
        execute all commands upto fi
  	fi
    
 Write Script as follows:
 
 ![Screen Shot 2021-01-28 at 12.39.52 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.39.52 AM.png)


Try it as follows:

![Screen Shot 2021-01-28 at 12.41.02 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.41.02 AM.png)

Detailed explanation:
First script checks whether command line argument is given or not, if not given then it print error message as "./ispos_n : You must give/supply one integers". if statement checks whether number of argument ($#) passed to script is not equal (-eq) to 0, if we passed any argument to script then this if statement is false and if no command line argument is given then this if statement is true. The echo command i.e.

echo "$0 : You must give/supply one integers"
| |
| |
1 2
1 will print Name of script
2 will print this error message

And finally statement exit 1 causes normal program termination with exit status 1 (nonzero means script is not successfully run).
The last sample run $ isnump_n 0 , gives output as "0 number is negative", because given argument is not > 0, hence condition is false and it's taken as negative number. To avoid this replace second if statement with if test $1 -ge 0.
    
- # **Nested if-else-fi**

You can write the entire if-else construct within either the body of the if statement of the body of an else statement. This is called the nesting of ifs.

![Screen Shot 2021-01-28 at 12.53.31 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.53.31 AM.png)

Run the above shell script as follows:

![Screen Shot 2021-01-28 at 12.55.09 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 12.55.09 AM.png)

Note that Second if-else constuct is nested in the first else statement. If the condition in the first if statement is false the the condition in the second if statement is checked. If it is false as well the final else statement is executed.

Syntax:

	if condition
		then
			if condition
		then
			.....
			..
			do this
		else
			....
			..
			do this
	fi
		else
			...
			.....
			do this
	fi

- # **Multilevel if-then-else**

Syntax:

	if condition
	then
		condition is zero (true - 0)
		execute all commands up to elif statement
	elif condition1
	then
		condition1 is zero (true - 0)
		execute all commands up to elif statement
	elif condition2
	then
		condition2 is zero (true - 0)
		execute all commands up to elif statement
	else
		None of the above condtion,condtion1,condtion2 are true (i.e.
		all of the above nonzero or false)
		execute all commands up to fi
	fi
   
For multilevel if-then-else statement try the following script:

![Screen Shot 2021-01-28 at 1.00.10 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 1.00.10 AM.png)


Try above script as follows:

![Screen Shot 2021-01-28 at 1.01.11 AM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 1.01.11 AM.png)

Above program gives error for last run, here integer comparison is expected therefore error like "./elf: [: -gt: unary operator
expected" occurs, but still our program notify this error to user by providing message "Opps! a is not number, give number".


- # **Loops in Shell Scripts**

Loop defined as:

"Computer can repeat particular instruction again and again, until particular condition satisfies. A group of instruction that is executed repeatedly is called a loop."

Bash supports:

- for loop
- while loop

Note that in each and every loop,

(a) First, the variable used in loop condition must be initialized, then execution of the loop begins.

(b) A test (condition) is made at the beginning of each iteration.

(c) The body of loop ends with a statement that modifies the value of the test (condition) variable.

### **for Loop**


	for { variable name } in { list }
	do
		execute one for each item in the list until the list is
		not finished (And repeat all statement between do and done)
	done
    
write the script as follows:

![Screen Shot 2021-01-28 at 5.54.19 PM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 5.54.19 PM.png)


Run it above script as follows:

![Screen Shot 2021-01-28 at 5.54.53 PM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 5.54.53 PM.png)


The for loop first creates i variable and assigned a number to i from the list of number from 1 to 5, The shell execute echo statement for each assignment of i. (This is usually know as iteration) This process will continue until all the items in the list were not finished, because of this it will repeat 5 echo statements.


Write a script to multiple a given number 10 times.

![Screen Shot 2021-01-28 at 5.56.33 PM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 5.56.33 PM.png)

Save above script and run it as:

![Screen Shot 2021-01-28 at 5.57.23 PM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 5.57.23 PM.png)

This happened because we have not supplied given number for which we want multiplication table, Hence script is showing Error message, Syntax and usage of our script. This is good idea if our program takes some argument, let the user know what is use of the script and how to used the script.

Note that to terminate our script we used 'exit 1' command which takes 1 as argument (1 indicates error and therefore script is terminated).

Even you can use following syntax:

	for (( expr1; expr2; expr3 ))
	do
		.....
		...
		repeat all statements between do and
		done until expr2 is TRUE
	Done

In above syntax BEFORE the first iteration, expr1 is evaluated. This is usually used to initialize variables for the loop.

All the statements between do and done is executed repeatedly UNTIL the value of expr2 is TRUE.
AFTER each iteration of the loop, expr3 is evaluated. This is usually use to increment a loop counter.

![Screen Shot 2021-01-28 at 6.05.32 PM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 6.05.32 PM.png)

Run the above script as follows:

![Screen Shot 2021-01-28 at 6.05.59 PM.png]({{site.baseurl}}/Screen Shot 2021-01-28 at 6.05.59 PM.png)

In above example, first expression (i = 0), is used to set the value variable i to zero.
Second expression is condition i.e. all statements between do and done executed as long as expression 2 (i.e continue as long as the value of variable i is less than or equel to 5) is TRUE.
Last expression i++ increments the value of i by 1 i.e. it's equivalent to i = i + 1 statement.


### **Nesting of for Loop**

The if statement can nested, similarly loop statement can be nested. You can nest the for loop. To understand the nesting of for loop see the following shell script.

![Screen Shot 2021-02-01 at 10.42.02 AM.png]({{site.baseurl}}/Screen Shot 2021-02-01 at 10.42.02 AM.png)


Run the above script as follows.

![Screen Shot 2021-02-01 at 10.42.35 AM.png]({{site.baseurl}}/Screen Shot 2021-02-01 at 10.42.35 AM.png)


Here, for each value of i the inner loop is cycled through 5 times, with the varible j taking values from 1 to 5. The inner for loop terminates when the value of j exceeds 5, and the outer loop terminets when the value of i exceeds 5.


Following script is quite intresting, it prints the chess board on screen.

![Screen Shot 2021-02-01 at 10.44.25 AM.png]({{site.baseurl}}/Screen Shot 2021-02-01 at 10.44.25 AM.png)


Run the above script as follows:

![Screen Shot 2021-02-01 at 10.45.02 AM.png]({{site.baseurl}}/Screen Shot 2021-02-01 at 10.45.02 AM.png)


Above shell script cab be explained as follows:

- **for (( i = 1; i <= 9; i++ ))** = Begin the outer loop which runs 9 times., and the outer
loop terminets when the value of i exceeds 9

- **for (( j = 1 ; j <= 9; j++ ))** = Begins the inner loop, for each value of i the inner loop is
cycled through 9 times, with the varible j taking values from 1 to 9. The inner for loop terminates when the value of j exceeds 9.

- **tot=`expr $i + $j`  
tmp=`expr $tot % 2`** = See for even and odd number positions using these
statements.

- **if [ $tmp -eq 0 ]; then**

  **echo -e -n "\033[47m "**

  **else**

  **echo -e -n "\033[40m "**

  **fi**  
  
If even number posiotion print the white colour block
(using echo -e -n "\033[47m " statement); otherwise for
odd postion print the black colour box (using echo -e -n
"\033[40m " statement). This statements are responsible to
print entier chess board on screen with alternet colours.


- **done = End of inner loop**

- **echo -e -n "\033[40m"** = Make sure its black background as we always have on our
terminals.

- **echo ""** = Print the blank line.

- **done** = End of outer loop and shell scripts get terminted by printing
the chess board.

**Exercise**

**1. Write shell script using for loop to print the following patterns on screen.**

![Screen Shot 2021-02-01 at 10.58.04 AM.png]({{site.baseurl}}/Screen Shot 2021-02-01 at 10.58.04 AM.png)


Script: 

![Screen Shot 2021-02-01 at 10.58.34 AM.png]({{site.baseurl}}/Screen Shot 2021-02-01 at 10.58.34 AM.png)

Output:

![Screen Shot 2021-02-01 at 11.01.18 AM.png]({{site.baseurl}}/Screen Shot 2021-02-01 at 11.01.18 AM.png)


**2.Write shell script using for loop to print the following patterns on screen.**

![Screen Shot 2021-02-01 at 10.59.50 AM.png]({{site.baseurl}}/Screen Shot 2021-02-01 at 10.59.50 AM.png)

Script:

![Screen Shot 2021-02-01 at 11.00.36 AM.png]({{site.baseurl}}/Screen Shot 2021-02-01 at 11.00.36 AM.png)

Output: 

![Screen Shot 2021-02-01 at 11.00.23 AM.png]({{site.baseurl}}/Screen Shot 2021-02-01 at 11.00.23 AM.png)


### **while loop**

Loop is executed as long as given condition is true.

Syntax:

	while [ condition ]
	do
		command1
		command2
		command3
		..
		....
	done

![Screen Shot 2021-02-02 at 8.53.53 AM.png]({{site.baseurl}}/Screen Shot 2021-02-02 at 8.53.53 AM.png)


Save it and try as

chmod 755 nt1

./nt1 7

Above loop can be explained as follows:

- n=$1 = Set the value of command line argument to variable n. (Here it's set to 7 )
- i=1 = Set variable i to 1
- while [ $i -le 10 ] = This is our loop condition, here if value of i is less than 10 then, shell execute all statements between do and done.
- do = Start loop.
- echo "$n * $i = `expr $i \* $n`" = Print multiplication table as 7 * 1 = 7 Here each time value of variable n is multiply be i.
- i=`expr $i + 1` = Increment i by 1 and store result to i. ( i.e. i=i+1).
- done = Loop stops here if i is not less than 10 i.e. condition of loop is not true. Hence loop is terminated.


### **The case Statement**

The case statement is good alternative to Multilevel if-then-else-fi statement. It enable you to match several values against one variable. Its easier to read and write.

Syntax:
	case $variable-name in
		pattern1) command
					...
					..
					command;;
		pattern2) command
					...
					..
					command;;
		patternN) command
					...
					..
					command;;
		*) command
					...
					..
					command;;
		esac
        
        
The $variable-name is compared against the patterns until a match is found. The shell then executes all the statements up to the two semicolons that are next to each other. The default is *) and its executed if no match is found.     


First script will check, that if $1(first command line argument) is given or not, if NOT given set value of rental variable to "*** Unknown vehicle",if command line arg is supplied/given set value of rental variable to given value (command line arg). The $rental is compared against the patterns until a match is found. For first test run its match with van and it will show output "For van Rs.10 per k/m." For second test run it print, "For car Rs.20 per k/m". And for last run, there is no match for Maruti-800, hence default i.e. *) is executed and it prints, "Sorry, I can not get a Maruti-800 for you".

![Screen Shot 2021-02-04 at 8.33.45 AM.png]({{site.baseurl}}/Screen Shot 2021-02-04 at 8.33.45 AM.png)

![Screen Shot 2021-02-04 at 8.38.34 AM.png]({{site.baseurl}}/Screen Shot 2021-02-04 at 8.38.34 AM.png)

Note that esac is always required to indicate end of case statement.




