# HW7. Recursion (Regular Expression) Exercise
## This is an Excercise. It is related to HW8.

<strong>Please read the entire file before you ask any question.</strong><br>

In this exercise you will learn how to use recursion for solving problems, and regular expressions (RegEx). RegEx is used mainly for pattern-matching, parsing, and filtering. Most importantly it is used by compilers such as gcc (C compiler) to translate the high level language to machine language. https://www.tutorialspoint.com/compiler_design/compiler_design_lexical_analysis.htm


# Learning Goals
* Use recursion to solve problems by dividing the problem into smaller problems.
* Understanding regular expressions.



# Functions you need to complete
In this exercise you will write three functions, for three different regex formulas rule1(), rule2(), rule3() in pe07.c, define protoypes in pe07.h, in the main() in main.c 

## Some of regular expression metacharacter syntax 
|    Pattern    |               Description                              |  
| ------------- | ------------------------------------------------------ |
|       ^       | Match the beginning of the string                      | 
|       $       | Match the end of the string                            |
|  \[a-zA-Z]    | Match English alphabet charachter                      |
|      \d	      | Match the digits                                       |
|    \[...]	    | Match any single character in brackets                 |
|      re*	    | Match 0 or more occurrences of the preceding expression|
|      re+	    | Match 1 or more of the previous thing                  |
| \[re1|re2]    | Match either expression re1 or re2                     |

Examples

A - "^\\d+$". This RegEx will match any Integer number.
	1- 5449 is a match.
	2- 45.5 is not a match because it has '.'.
	3- a448 is not a match because it has 'a'.
	
B - "^\[\\d|0]+\[.]\\d+$". This RegEx will match any number that starts with 1+ numbers followed by '.' followed by and ends by 1+ numbers and must end with a number.
	1- 215.565 is a match.
	2- 0.25 is a match.
	3- .25 is not a match because it does not start with a number.
	4- 25. is not a match because it does not end with a number.

C - "^\[\[a-zA-Z]|_]\[\[a-zA-Z]||\\d|_]*$". This RegEx will match a vaild identifier which is any word that start with '_' or alphabetical character followed by 0+ alphanumerical characters or '_'. 
	1- _12 is a match.
	2- _A23A2____54 is a match
	3- 1_asdj21 is not a match because it does not start with '_' or alphabetical character. 
	4- _qas@ is not a match because it contains '@' which is not alphanumerical nor '_'.
	
D - "^\[a]\[\[\[a-zA-Z]||\\d]]*$". This RegEx will match any word that starts with 'a' followed by 0+ alphanumerical characters and must end with either a or alphanumerical character. 
	1- "asw1234" is a match.
	2- "a12q" is a match.
	3- "bas2312" is not a match because it does not start with 'a'.
	4- "a@fs" is not a match because it contains "@" which is not alphanumerical.





In this exercise, you have to complete three functions - `Connect()`, `Close()`, `SearchByName()` in `pe04.c`, `main()` in `main.c`, and define `Student` structure in the `pe04.h` file.

1. `Connect()` - Read the content in the file and allocate appropriate memory to store the content. This function accepts only one argument:
	1. filename: the filename of the database you are going to connect.
	2. You may want to use: `fopen()`, `fclose()`, `fscanf()`, `feof()` to read the file content.
	3. This function returns a pointer to `StudentDatabase` object. 
2. `Close()` - This function releases the memory you allocated in `Connect()` and close the database. Not completing this function will lead to memory leak. This function has one argument:
	1. studb: the pointer to `StudentDatabase` object of which the memory needs to be freed.   
3. `SearchByName()` - This function searches the student by name in database. It accepts two arguments:
	1. studb: the pointer to `StudentDatabase` object where you will search for the student.
	2. name: the name of the student you are looking for.
	3. This function should return a `NULL` if the name is not in the database, otherwise it should return a pointer to the `Student` structure which stores all the info of that student. 
4. `main()` - In this exercise, you will learn to use `argc` and `argv`. Here are the specifications.
	1. `argc`: If `argc` is less than 3, you should return `EXIT_FAILURE` and print "Insufficient arguments\n".
	2. `argv[1]`: name of the input file.
	3. `argv[2]`: should be either "-a", or "-s".
 			When `argv[2]` is "-a", you should print all the students in database using `PrintDatabase()` function and return `EXIT_SUCCESS`.
 			When `argv[2]` is "-s', you should  enter the name of the student in `argv[3]` and print information of that student, if there is no input in `argv[3]` you should print "Wrong arguments\n" and return `EXIT_FAILURE`.
			If `argv[2]` is neither "-a" nor "-s", you should print "Wrong arguments\n" and return `EXIT_FAILURE`
	4. `argv[3]`: We only need input in `argv[3]` when `argv[2]` is equal to "-s". `argv[3]` is the name of the student you are looking for. If there is no such student, you should print "No this student\n". Otherwise, use `PrintStudent()` function to print the information of the student.
5. Define `Student` structure in pe04.h: The `Student` structure has 6 fields, we have deifned 2 of them for you. Complete the remaining 6 fields. See `pe04.h` for further information.

# Testing your code
Following are the files we provide:
1. `pe04.c` - Define your functions in this assignment.
2. `pe04.h` - Header file, which has definition for the functions and structures you need in this assignment.
3. `main.c` - main file of this assignment.
4. `database.txt` - This is the database file which stores all student's info.
5. `output1.txt` - This is an example output when you run `./pe04 database.txt -a`
6. `output2.txt` - This is an example output when you run `./pe04 database.txt -s name`
	Note that this file has multiple lines because we run the command with different names.
7. `output3.txt` - This is an example output when you run `./pe04` with wrong argc or argv arguments. 
	Differnt types of argc, argv errors leads to different output. 


To test your code. You have to first compile it and then run the following command.

Print all student info in database.
```
./pe04 database.txt -a
```
Print the student you are looking for in database.
```
./pe04 database.txt -s name
```
1. pe04 - This is binary that should get generated
2. database.txt - This is the database file which stores all students' information.
3. "-a", "-s" - These are the arguments you should specify. "-a" means to print all the information in the database. "-s" means to print the information of the student you are looking for. 
4. name - name of the student you are looking for. You only have to input this argument when `argv[2]` is "-s".

# Checking for memory errors
You should also run./pe04 with arguments under valgrind. To do that, you have to use, for example, the following command:
```
valgrind --log-file=memcheck.log ./pe04 database.txt -a
```
and
```
valgrind --log-file=memcheck.log ./pe04 database.txt -s name
```
Note that you should use other input arguments to extensively test your function. If you follow the instructions and keep the malloc and free functions in the right place, you should not have memory problems in this assignment.


# Submitting Your code
** This is a programming exercise, so you would have to submit the code on Blackboard.**

You have to submit the following file in a <strong>zip</strong> folder on the blackboard:
* `pe04.c` - This file should have `Connect()`, `Close()`, `SearchByName()` functions completed.
* `pe04.h` - This file should have `Student` structure defined.
* `main.c` - This file should have `main()` function completed.
<strong>You will not get any credits if the submitted file is not zipped</strong>

The **only** way to submit homework is through Blackboard.

The instructor will **never** accept any requestion for exception "*my
submission is only one minute late*".  It is your responsibility to
meet the deadline.  You are strongly encouraged to submit at least ten
minutes before the deadline because submission may take time.

If there is a campus-wide problem (such as network outage or the
Blackboard server is down), the deadline will be extended for the
entire class. If the problem is specific to yourself (for example,
your computer crashes), the deadline will not be extended for
you.

**DO NOT** send your code by email. Your code will not be graded
  if it is sent by email.

The teaching staff is strictly prohibited to look at files on your
computer (or your Purdue account) for grading. Thus, **NEVER** say "I
finished before the deadline but I forgot to submit".  **NEVER** say "I have
not made any change after the submission deadline." because the
teaching staff is not allowed to look at your files that have not been
submitted through Blackboard.

# Grading
If your program has any compilation error or warning (remember to use
`gcc -std=c99 -g -Wall -Wshadow --pedantic -Wvla -Werror`), you will
receive zero in this assignment.

In absolutely no circumstance can the teaching staff modify your
program for grading.  You cannot say, "If you change this, my program
works." If your program misses a semicolon and cannot compile, you
will receive zero.  Your score depends on what is submitted, nothing
else.

This exercise will be graded as folows:
1. `Student` structure: whehter the structure is properly defined.
2. `Connect()` function: whether you successfully connect to database.txt.
3. `Close()` function: whether you release all the allocated memory.
4. `SeachByName()` function: whether your function meets the specification as described above. 
5. `argc` and `argv`: whether the main function meets the specifications as described above.
6.  Code that contains memory problems reportable by Valgrind will be subject to a penalty of 40% of the total possible points.
