---
title: lab1-password
published: 2024-07-25
description: 'python lab1-password'
image: ''
tags: [python]
category: 'python'
draft: false 
---
## <u>introduction</u>
The goal of this assignment is to familiarize you with loops. In Part 1, you will practice various different types of loops. In Part 2, you
will implement a program to help a user choose a strong password.
## <u>part 1</u>
This part will give you practice using different types of loops.
Create a new project named `PasswordChecking` in the `CSCI51p-Workspace` you created on your Desktop. <b>Double check that you are
creating the project in the right place, or you will likely have trouble finding your files later.</b> Then download the <u>loops.py</u> starter
file for part one and copy it into the (recently created) `CSCI051p-Workspace/PasswordChecking` folder. If you don't see the new file,
ask PyCharm to rescan that folder by clicking the triangle next to that folder (on the left-side list) to close and re-open it. The newly
added `loops.py` should now be visible. If you double-click it (in the left-side list), that file should appear in the main editing window.
Inside the file you should see three problems, each followed by a single-line comment `# TODO`. Replace each of these `# TODO`
comments with a solution to that problem.
### Problem 1
Implement Python code that asks the user to choose their favorite primary color (red, yellow, or blue) and counts how many tries it
takes them to choose a color. You must use a while-loop to solve this problem. It is fine to ignore capital letters.
The following is a sample run:
```
What is your favorite primary color: red, yellow, or blue?
green
That is not a primary color. What is your favorite primary color?
13
That is not a primary color. What is your favorite primary color?
red
You chose red after 3 tries. 
```
### Problem 2
Implement Python code that asks the user for two positive integers and then prints the sum of the even numbers between those
integers. If one of those integers is an even number, you should include that value. For this problem, you may assume that your user
correctly follows instructions and the first number entered is smaller than the second one. You must use a for-loop to solve this
problem.
The following is a sample run:
```
Enter an integer:
1
Enter another integer
10
The sum of the even numbers in the range [1, 10] is 30
```
### Problem 3
Implement Python code that asks the user for a string and then counts the number of vowels (a, e, i, o, or u) that appear in that
string. You may assume that the user uses only lower case letters. You must use a for-loop to solve this problem
The following is a sample run:
```
Enter a string:
Hello there
"Hello there" contains 4 vowels
```
### Checking In
Find a TA or your lab instructor and demo your code. They will look over your code, ask you to run your code with various different
inputs, and award you points for Part 1.
This must be completed before leaving the lab. After that you should start working on Part 2.
## <u>part 2</u>
A new startup, CoolGamzRUs, needs its users to choose a username and password when they create a new account. However,
CoolGamzRUs would like to make sure that its users do not choose weak passwords (such as `123456`), so it would like to enforce
certain rules about what passwords may be chosen. They hire you to write a program that will help their users choose a strong password.
### Specification
You will write an interactive program that helps a user to choose a strong password.
First write a program that starts by prompting the user to enter a password. If the user enters a strong password, the program will
tell the user that it is a valid password. If the user enters a weak password, the program will tell the user what is wrong with their
password.
CoolGamzRUs defines a strong password as follows:
• Password should contain at least 8 characters
• Password should contain at least 2 lowercase letters
• Password should contain at least 1 uppercase letter
• Password should contain at least 2 numbers
• Password should contain at least 1 of the characters !@#$
If the user enters a password that passes all five rules, the program should print `Password is a valid password` and then finish. If
the user enters a weak password, the program should print the first rule that the password fails (using the order given above).
The following are sample runs:
```
Please enter your password:
123456
Password should contain at least 8 characters
Please enter your password:
password
Password should contain at least 1 uppercase letter
Please enter your password:
Fall2022!
Password Fall2022! is a valid password
```
Now modify your code from Part A so that it keeps asking the user to enter a password until they enter a strong password.
<b>Note: your program must match the wording and formatting of the sample run exactly. We will use programs to check your
program for correctness, and our grading program will only give you credit if you use the correct wording and spacing.
Please double check this, and talk to an instructor or TA if you are unsure.</b>
The following is a sample run:
```
Please enter your password:
123456
Password should contain at least 8 characters
Please enter your password:
12345678
Password should contain at least 2 lowercase letters
Please enter your password:
password
Password should contain at least 1 uppercase letter
Please enter your password:
Password
Password should contain at least 2 numbers
Please enter your password:
fall2022
Password should contain at least 1 uppercase letter
Please enter your password:
Fall2022
Password should contain at least 1 of the characters !@#$
Please enter your password:
Fall2022!
Password Fall2022! is a valid password
```
### Getting Started
There is a starter file <u>password_checking.py</u> provided for this assignment. Download the file `password_checking.py` and copy it into
the (recently created) `CSCI51p-Workspace/PasswordChecking` folder.
###　Hints and Suggestions
You will probably need to use two nested loops to implement this program: one loop to go through the string the user entered and
check whether it is a strong password (the first portion of Part 2) and one loop to prompt the user to enter another password until
they enter a strong password (the second portion of Part 2). Think about whether you want to use a while-loop or a for-loop for each
of these pieces.
Relational operators `<, <=, >, >=` work on strings! These operators compare strings using lexicographic order, what you might think of
as the order words appear in a dictionary. So `"aaa" < "ab"` and `"ab < ac"`. Note that in Python, as in most other programming
languages, any upper case letter is considered "less than" any lower case letter (because of their ASCII encodings), so `"aBc"` <
`"aaa"`
### Coding Style
Make sure that your program is properly commented:
• You should have a multi-line comment at the very beginning of the file stating your name, course, assignment number, and the
date.
• You should include meaningful one-line comments that explain what your code is doing throughout your program.
In addition, make sure that you have used good style. This includes:
• Following naming conventions, e.g. all variables and functions should be lowercase and words should be separated with an
underscore.
• Using good (mnemonic) variable names.
• Proper use of whitespace, including indenting and use of blank lines to separate chunks of code that belong together.
For more detailed descriptions, please review the <u>Python Coding Style Guidelines</u>.
```python
def check_password(password):
    if len(password) < 8:
        return False, "Password should contain at least 8 characters"

    lowercase_count = sum(1 for c in password if c.islower())
    if lowercase_count < 2:
        return False, "Password should contain at least 2 lowercase letters"

    uppercase_count = sum(1 for c in password if c.isupper())
    if uppercase_count < 1:
        return False, "Password should contain at least 1 uppercase letter"

    number_count = sum(1 for c in password if c.isdigit())
    if number_count < 2:
        return False, "Password should contain at least 2 numbers"

    special_count = sum(1 for c in password if c in "!@#$")
    if special_count < 1:
        return False, "Password should contain at least 1 of the characters !@#$"

    return True, f"Password {password} is a valid password"

def main():
    while True:
        password = input("Please enter your password:\n")
        is_valid, message = check_password(password)
        print(message)
        if is_valid:
            break

if __name__ == "__main__":
    main()
```