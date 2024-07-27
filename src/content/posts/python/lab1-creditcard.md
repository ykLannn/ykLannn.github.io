---
title: lab1-creditcard
published: 2024-07-25
description: 'python lab1-creditcard'
image: ''
tags: [python]
category: 'python'
draft: false 
---
## <u>introduction</u>
The goal of this assignment is to give you more practice with functions, including testing functions and modeling function call behavior with stack frames. For this assignment, you will implement functions that take a variety of parameter types and return a variety of types.
<b>Note: in this assignment, all of your processing MUST be on integers. You are not allowed to convert integer numbers or parameters into strings for processing.</b>
## <u>part 1</u>
Create a new project named `CreditCards` in the `CSCI51p-Workspace` you created on your Desktop. **Double check that you are
creating the project in the right place, or you will likely have trouble finding your files later.** Then download the [starter code](http://www.cs.pomona.edu/classes/cs51p/assignments/a4/cc.zip)
and unzip the file (on a Mac, unzipping will happen automatically). You should see a folder named `starter` that contains two files
(`creditcard_part1.py` and `creditcard.py`). Copy both files into the (recently created) `CSCI51p-Workspace/CreditCards` folder.

Now open the file `creditcard_part1.py`. Your job for Part 1 is to implement the four functions in that file as described below.

### last_digit
Implement the helper function `last_digit` which takes a positive integer and returns the last digit of that integer.
When you believe your function is working correctly, please call it in the main function with different arguments to make sure it
works, e.g., `last_digit(23)` should have the return value of 3, `last_digit(47)` should have the return value of 7.
### decimal_right_shift
Go back to the file `creditcard_part1.py` and implement the function `decimal_right_shift`, which takes an integer and returns the
number constructed by removing the last digit. For example, `decimal_right_shift(123)` should evaluate to 12

When you believe your function is working correctly, please call it in the main function with different arguments to make sure it
works.
### sum_digits
Go back to the file `creditcard_part1.py` and implement the function `sum_digits`, which takes a 3-digit integer as a parameter and
returns the (integer) sum of the digits. You may assume that the value passed as an arugment to sum_digits is always a positive 3-
digit integer. Hint: you will want to use the functions `last_digit` and `decimal_right_shift` as helper functions! Remember to add a
docstring for this function.

When you believe your function is working correctly, please call it in the main function with different arguments to make sure it
works.
### main
Implement the `main` function in `creditcard_part1.py`, which should repeatedly asks the user for a 3-digit positive integer until they
do so and then print the sum of those digits (obtained by calling `sum_digits`). Remember to add a docstring for your main function!
Note: users are allowed to enter the string like `"000"`, which is equal to 0 that is not a 3-digit number. So, you need to find a proper
way to ensure a 3-digit number is entered.

Note: you also need to test your main function by enterring different input to interact with your program.

The following is a sample run:
```
Please enter a 3-digit positive integer:
 257
The sum of the digits of 257 is 14
```
### Checking in
Before finding a TA or professor, make sure your functions have

>• appropriate docstrings

>• good algorithm comments

>• mnemonic variable names

>• good use of horizontal and vertical white space

We will double check your code and your test cases, ask you a few questions about it, answer any questions you have, and award
your points for Part 1.

This must be completed before leaving the lab. After that you should start working on Part 2.

```python
def last_digit(num):
    """
    Computes the last digit of the num

    :param num: (int) a positive integer
    :return: (int) the last digit of num
    """
    return num % 10



def decimal_right_shift(num):
    """
    Right shifts num by one digit

    :param num: (int) a positive integer
    :return: (int) num right shifted by one digit
    """
    return num // 10



def sum_digits(num3):
    """
    Sums the digits of a three-digit number

    :param num3: (int) a positive, three-digit number
    :return: (int) the sum of the digits of num3
    """
    digit1 = last_digit(num3)
    num3 = decimal_right_shift(num3)
    digit2 = last_digit(num3)
    num3 = decimal_right_shift(num3)
    digit3 = last_digit(num3)

    return digit1 + digit2 + digit3

    # sum_digits = 0
    # while num3 > 0:
    #     sum_digits += num3 % 10
    #     num3 //= 10
    #
    # return sum_digits

def main():
    """
    Asks user for a 3-digit positive integer until a valid input is given,
    then prints the sum of its digits.
    """
    while True:
        try:
            num_str = input("Please enter a 3-digit positive integer: ")
            num = int(num_str)
            if 100 <= num <= 999:
                sum_of_digits = sum_digits(num)
                print(f"The sum of the digits of {num} is {sum_of_digits}")
                break
            else:
                print("Invalid input. Please enter a valid 3-digit positive integer.")
        except ValueError:
            print("Invalid input. Please enter a valid 3-digit positive integer.")

if __name__ == "__main__":
    main()
```
## <u>part 2</u>
### Background Information - Valid credit card numbers
What makes a credit card number valid? For our purposes, we'll assert that a number is valid if it passes the Luhn algorithm. (In
practice there are also additional restrictions. For example, all Visa cards must start with the number 4)

An algorithm is a set of instructions for accomplishing a specific task, so the Luhn algorithm is a set of instructions for checking
whether a number is potentially a valid credit card number. You can read more about credit card numbers in [this article](https://www.forbes.com/advisor/credit-cards/what-does-your-credit-card-number-mean/).

To see how the Luhn algorithm works, let us use it to validate the number `9813428854407`:
1. Double the value of alternate digits of the credit card number beginning with the second digit from the right (the first right-hand digit is the check digit).
`9 16 1 6 4 4 8 16 5 8 4 0 7`
2. Add the individual digits comprising the products obtained in Step 1 to each of the unaffected digits in the original number.
`9 + (1+6) + 1 + 6 + 4 + 4 + 8 + (1+6) + 5 + 8 + 4 + 0 + 7 = 70`
3. If the total obtained in Step 2 is a number ending in zero (`30, 40, `50`, etc.), then the account number is valid. `70` ends in a `0`,
so the account number is valid.

Before you continue, please make sure you fully understand the Luhn algorithm and how it checks numbers for validity! It doesn't
make sense to try to implement an algorithm until you understand how it works. (Please feel free to discuss the algorithm with other
students, the TAs, the professors, etc!) Make sure you understand the algorithm well enough to answer the following questions:

>• Is `1234567890123` a valid number?

>• If the first 12 digits of a 13-digit credit card number are `111111111111`, what must the 13th digit be?

### Specifications
All the code for this assignment should implemented in the file `creditcard.py`. Please read the assignment specification carefully to
make sure that you submit all the required components.

Your program will ask the user for a 6 digit number, then generate three valid 13 digit credit card numbers each starting with those
initial 6 digits.

Your program must implement the following functions. You may also choose to define additional functions, if you'd like. For example,
you could define a helper function that computes the Luhn sum for a number. If you do define any helper functions, we strong
encourage you to add test cases for your helper functions!

Note: The line at the top of `creditcard.py` imports the functions `last_digit` and `decimal_shift_right` from the file
`creditcard_part1.py`, so your program should make use of the helper functions from `creditcard_part1.py` --- don't reinvent the
wheel!! Failing to call helper functions when appropriate will result in a loss of style points.

### Luhn Sum
The `luhn_sum` function takes a 13 digit integer as input and returns the Luhn sum of that number (i.e., the value you get at the end of
Step 2 above).

After you think your function is working correctly, you should test your function with different input arguments and compare the
return value with the expected result.

Hint: You'll want to use the functions you defined in Part 1! Also, remember to add a docstring!

### Verify
The `verify` function takes a 13 digit integer as input and returns `True` if the number passes the Luhn algorithm and `False` if it fails.

After you think your function is working correctly, you should test your function with different input arguments and compare the
return value with the expected result.

You may find it helpful to use a [website](https://planetcalc.com/2464/#google_vignette) to verify whether numbers actually satisfy the Luhn algorithm.

Hint: remember to use the functions you've defined thus far and to add a docstring for your function!

### Generate
The `generate` function takes a 6 digit integer and returns a valid 13 digit credit card number which begins with the given 6 digits.
The return value must be of type `int`.

Hint: the 6 randomly generated digits must be selected from the full range from 0 through 9.

After you think your function is working correctly, you should test your function with different input arguments and compare the
return value with the expected result.

Hint: remember to use the functions you've defined thus far and to add a docstring for your function!

### Main
The `main` function asks the user for an initial 6 digit number, then generates and prints three valid credit card numbers that start with
those 6 numbers. See example run below. Remember to add a docstring for your main function!

The following is a sample run:
```
Enter a 6 digit number:
981342
Three valid numbers:
9813428854407
9813424039581
9813420046028
```
### Hints and Suggestion
Some questions to think about before you start writing code:
• The Luhn algorithm works on digits, but the verify and generate functions take integers. You will want to use your helper
functions from Part 1 to break integers into digits.
• Having generated digits, how will you reassemble them into a number?
Random Numbers
Python is popular in part because there are many modules and packages that are available to use. If, for example, you need to
generate random numbers, you can use the random module. In order to do so, you first need to tell the interpreter that you want to
use that module. There are different ways to do this, but the one we'll use requires naming the exact functions that we want from the random module.
Taking a look at the random documentation, we see that randint will enable us to generate a random integers within a given range.
To use this we must add the following line at the beginning of our program (right after that multi-line comment that's at the top of all
our programs):
from random import randint
This allows us to use the randint function as if it was defined in our code.
Coding style
Make sure that your program is properly commented:
• You should have comments at the very beginning of the file stating your name, course, assignment number and the date.
• Each function should have an appropriate docstring, describing:
◦ the purpose of the function
◦ the types and meanings of each parameter
◦ the type and meaning of the return value(s)
• Include other comments as necessary to make your code clear
In addition, make sure that you've used good style. This includes:
• Following naming conventions, e.g. all variables and functions should be lowercase.
• Using good (mnemonic) variable names.
• Proper use of whitespace, including indenting and use of blank lines to separate chunks of code that belong together.
```python
from random import randint
from creditcard_part1 import last_digit, decimal_right_shift


def luhn_sum(number13):
    """Calculate the Luhn sum for a 13-digit number."""
    total_sum = 0
    is_second = False

    while number13 > 0:
        digit = last_digit(number13)
        if is_second:
            doubled_digit = digit * 2
            total_sum += doubled_digit if doubled_digit < 10 else doubled_digit - 9
        else:
            total_sum += digit
        number13 = decimal_right_shift(number13)
        is_second = not is_second

    return total_sum

def verify(number13):
    """Verify if the 13-digit number is valid according to the Luhn algorithm."""
    return luhn_sum(number13) % 10 == 0

def generate(number6):
    """Generate a valid 13-digit credit card number starting with the given 6 digits."""
    # Start with the 6 provided digits
    base_number = number6 * 10**7

    # Generate the next 6 digits randomly
    for _ in range(6):
        base_number = base_number * 10 + randint(0, 9)

    # Calculate the last digit (check digit) to make the number valid
    luhn_sum_val = luhn_sum(base_number * 10)
    check_digit = (10 - (luhn_sum_val % 10)) % 10

    return base_number + check_digit

def main():
    """Main function to generate and display three valid 13-digit credit card numbers."""
    while True:
        try:
            number6 = int(input("请输入一个6位数字: "))
            if 100000 <= number6 <= 999999:
                break
            else:
                print("请输入一个有效的6位数字。")
        except ValueError:
            print("输入无效，请输入一个有效的6位数字。")

    print("三个有效的信用卡号码:")
    for _ in range(3):
        print(generate(number6))

if __name__ == "__main__":
    main()
```