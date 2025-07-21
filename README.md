Set A 

1) Write a Python program that simulates a basic calculator, performing addition, subtraction, 
multiplication, and division.
 
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))
op = input("Enter operation (+, -, *, /): ")

if op == '+':
    print("Result:", a + b)
elif op == '-':
    print("Result:", a - b)
elif op == '*':
    print("Result:", a * b)
elif op == '/':
    if b != 0:
        print("Result:", a / b)
    else:
        print("Cannot divide by zero.")
else:
    print("Invalid operator")



2) Write a Python program that converts a given decimal number to its binary equivalent. 

num = int(input("Enter a decimal number: "))
print("Binary:", bin(num)[2:])



3) Write a Python program that asks for the user's age and then prints a message stating whether 
the user is a minor, an adult, or a senior. 

age = int(input("Enter your age: "))
if age < 18:
    print("You are a minor.")
elif age < 60:
    print("You are an adult.")
else:
    print("You are a senior.")



4) Write a Python program to swap the values of two variables without using a third variable. 

a = int(input("Enter first number: "))
b = int(input("Enter second number: "))
a, b = b, a
print("After swapping: a =", a, ", b =", b)



5) Write a Python program to print the first 10 numbers of the Fibonacci series. 

a, b = 0, 1
for _ in range(10):
    print(a, end=' ')
    a, b = b, a + b


6) Write a Python program to check if a given number is prime or not. 

num = int(input("Enter a number: "))
if num > 1:
    for i in range(2, int(num**0.5)+1):
        if num % i == 0:
            print("Not a prime number.")
            break
    else:
        print("Prime number.")
else:
    print("Not a prime number.")



7) Write a Python program that takes three numbers as input and checks if the third number is the 
sum of the first two numbers using logical operators.

a = int(input("Enter first number: "))
b = int(input("Enter second number: "))
c = int(input("Enter third number: "))

if c == a + b:
    print("Third number is the sum of the first two.")
else:
    print("Third number is not the sum.")


 
8) Write a Python program that imports a custom module you created with a function that returns 
the factorial of a number. 

# mymath.py
def factorial(n):
    result = 1
    for i in range(2, n+1):
        result *= i
    return result


import mymath

num = int(input("Enter a number: "))
print("Factorial:", mymath.factorial(num))



9) Write a Python program that takes two numbers as input and performs division, handling the 
case where the divisor is zero. 

a = float(input("Enter numerator: "))
b = float(input("Enter denominator: "))

if b == 0:
    print("Cannot divide by zero.")
else:
    print("Result:", a / b)




10) Write a Python function that takes a list of numbers and returns the maximum value in the list. 

def find_max(lst):
    return max(lst)

print(find_max([10, 20, 5, 100]))


 
11) Write a Python function that takes a name and an optional age parameter and prints a greeting. 
If the age is not provided, it should default to 25. 

def greet(name, age=25):
    print(f"Hello {name}, you are {age} years old.")

greet("Alice")
greet("Bob", 30)



12) Write a Python program to count the number of vowels in a given string. 

text = input("Enter a string: ")
count = sum(1 for ch in text.lower() if ch in "aeiou")
print("Number of vowels:", count)



13) Write a Python program that prints a multiplication table up to (numberx10). 

num = int(input("Enter a number: "))
for i in range(1, 11):
    print(f"{num} x {i} = {num * i}")



14) Write a Python program to print a right-angled triangle of '*' with a given number of rows. For 
example, if the number of rows is 5, the output should be: 
*  
**  
***  
****  
*****

rows = int(input("Enter number of rows: "))
for i in range(1, rows + 1):
    print("*" * i)


 
15) Write a Python program to print a pyramid of '*' with a given number of rows. For example, if 
the number of rows is 5, the output should be: 
*  
***  
*****  
*******  
********* 

rows = int(input("Enter number of rows: "))
for i in range(1, rows + 1):
    spaces = ' ' * (rows - i)
    stars = '*' * (2 * i - 1)
    print(spaces + stars)



Set B
1) Given an integer x, return true if x is a palindrome, and false otherwise. (LeetCode: Palindrome 
Number) 

def is_palindrome(x):
    return str(x) == str(x)[::-1]

# Example
print(is_palindrome(121))  # True
print(is_palindrome(-121)) # False



2) Given a non-empty array of integers nums, every element appears twice except for one. Find 
that single one. (LeetCode: Single Number) 

def single_number(nums):
    result = 0
    for num in nums:
        result ^= num
    return result

# Example
print(single_number([2, 2, 1]))  # 1



3) Given an array of integers nums and an integer target, return indices of the two numbers such 
that they add up to target. You may assume that each input would have exactly one solution, 
and you may not use the same element twice. You can return the answer in any order. 
(LeetCode: Two Sum) 

def two_sum(nums, target):
    seen = {}
    for i, num in enumerate(nums):
        diff = target - num
        if diff in seen:
            return [seen[diff], i]
        seen[num] = i

# Example
print(two_sum([2, 7, 11, 15], 9))  # [0, 1]



4) Write an algorithm to determine if a number n is happy. (LeetCode: Happy Number) 

def is_happy(n):
    seen = set()
    while n != 1 and n not in seen:
        seen.add(n)
        n = sum(int(ch) ** 2 for ch in str(n))
    return n == 1

# Example
print(is_happy(19))  # True



5) Given an integer array nums, return true if any value appears at least twice in the array, and 
return false if every element is distinct. (LeetCode: Contains Duplicate)

def contains_duplicate(nums):
    return len(nums) != len(set(nums))

# Example
print(contains_duplicate([1, 2, 3, 1]))  # True
