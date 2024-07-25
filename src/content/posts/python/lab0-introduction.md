---
title: lab0-introduction
published: 2024-07-23
description: 'python lab0-introduction'
image: ''
tags: [python]
category: 'python'
draft: false 
---
## <u>introduction</u>
The goal of this assignment is to familiarize you with the core concepts of programming languages---values, types, and
operations---and to introduce you to the basic functionality of the Python programming language. In Part 1, you will explore the
concepts of *value* and *type*. In Part 2, you will implement an interactive program using conditionals.
## <u>part 1</u>
After starting PyCharm you can go to the top left of your screen, click on the `File` button, and select `New Project`. Go ahead and
create the project, making sure that the location of the project is a new sub-folder (e.g. `Introduction`) in the `CSCI51p-Workspace`
you created on your Desktop last week.
Download the starter file for part one, `introduction_part1.py` and copy it into the (recently created) `CSCI51p-Workspace/
Introduction` folder. Then ask PyCharm to rescan that folder by clicking the triangle next to that folder (on the left-side list) to close
and re-open it. The newly added `introduction_part1.py` should now be visible. If you double-click it (in the left-side list), that file
should appear in the main editing window.
### Values and Types
Observe that the starter file contains a simple, one-line program:
```python
print("Hello world!")
```
What happens when you run this program?
Recall that the easiest way to run a program that you are editing is to place the cursor in the file editing window and right-click. One
of the options will be `Run` (and the name of the currently selected file); select this option. You can also selection option `Run` from the
`Run` menu.
What happens if you change that line to the following?
```python
print('Hello world!')
```
How about this?
```python
print(Hello world!)
```
There is a way to find out the type of a value in Python. Try putting the following three lines of code in your Python file and compare
it to what happened before.
```python
print(type("Hello world!"))
print(type('Hello world!'))
print(type(Hello world!))
```
Given their types, what might you hypothesize about the print function?
You will not need to demonstrate any code for this part; you will just need to explain your hypothesis during your lab check-in. You
probably want to comment out any print statements remaining from this part before proceeding.
###　Expressions and Types
Now let's explore the ideas of value and type a bit more. Determine what the following expressions evaluate to (value and type):
1. 3/2
2. 3.0/1
3. "3/2"
4. "3"/2
5. 3*2
6. 3.0*2
7. "3*2"
8. "3"*2
```python
print(type(3/2))<class 'float'>
print(type(3.0/1))<class 'float'>
print(type("3/2"))<class 'str'>
# print(type("3"/2))
print(type(3*2))<class 'int'>
print(type(3.0*2))<class 'float'>
print(type("3*2"))<class 'str'>
print(type("3"*2))<class 'str'>
```
How would you explain your results? You might want to play around a bit more with other expressions to make sure your explanation
generalizes.
You will not need to demonstrate any code for this part; you will just need to describe the explanation you came up with during your
lab check-in. You probably want to comment out any print statements remaining from this part before proceeding.
Using Expressions
Consider the following word problems:
1. Last night Cecil went to sleep at 11:00pm. This morning he woke up at 8:27am. How many seconds of sleep did he get?
2. What is the ratio of the amount of sleep that Cecil got last night to the amount of sleep that you got last night?
Write a program in your file `introduction_part1.py` that solves these two problems and prints out each of the solutions.
Checking In
Call over an instructor or TA to discuss your explanations for "Values and Types" and "Expressions and Types" and to check your
code from "Using Expressions". If you have been successful thus far, they will award your points for Part 1.
This must be completed before leaving the lab. After that you should start working on Part 2.
## <u>part 2</u>
For this part, you will write a program which interacts with the user. Download the starter file for part two, introduction.py, and copy it
into your CSCI51p-Workspace/Introduction folder. Then ask PyCharm to rescan that folder by clicking the triangle next to that
folder (on the left-side list) to close and re-open it. The newly added introduction.py should now be visible. If you double-click it
(in the left-side list), that file should appear in the main editing window.
Observe that this file currently contains a multi-line comment at the top. Edit this comment to include your name, and then write an
interactive program in this file.
Specification
For full credit, your program must do each of the following:
• Ask the user for at least two piecfes of information about themselves
• Display some response that both says something about the program and relates it in some meaningful way to the information
the user gave you.
In addition, the way in which your code accomplishes the above must satisfy the following requirements:
• Use the input() funciton
• Use (at least) one variable
• Use (at least) two of the operators +,-,/,*,**,//,%
• Operate (at least) once on something of type int or float
• Operate (at least) once on something of type str
• Use (at least) two conditional expressions (i.e., if statements)
Example
The previous section outlines the requirements. You're strongly encouraged to exercise your creativity in satisfying them! The
following is an example of a program that satisfies the (minimum) requirements. (Yes, you'll have to take our word for it that the
underlying code satisifes the implementation requirements... note the distinction between *what* something is doing and *how* it
does it!)
```python
*******************************************************************************
What is your name?
Cecil
Hi Cecil!
It is nice to meet you. My name is Yi Chen. I am a professor at Pomona
College. I've been at Pomona for over 20 years and I think I have an
amazingly wonderful (although occasionally stressful) job.
Pick a number
60
I am fond of the number 13, which is 47 less than 60.
I also like tea, hiking, and quiet reading time. Do you like tea?
Yes
Great! I'm happy to hear that!
Bye!
*******************************************************************************
```
```python
def main():
    name = input("What is your name? ")
    age = int(input("How old are you? "))

    nextAge = age + 1
    halfAge = age / 2

    print(f"Hello, {name}!")
    print(f"Next year you will be {nextAge} years old.")
    print(f"Half of your current age is {halfAge}.")

    if age % 2 == 0:
        print("Your age is even.")
    else:
        print("Your age is odd.")

if __name__ == "__main__":
    main()
```