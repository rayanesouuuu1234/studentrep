---
toc: False
comments: False
layout: post
title: ALGORITHMS
description: Team SRSC
type: hacks
courses: {'csp': {'week': 7}}
---

# ALGORITHMS 
## SRSC 


# <mark>BIG IDEA: A FINITE SET OF INSTRUCTIONS THAT ACCOMPLISH A SPECIFIC TASK 



## SEQUENCING 

### <mark> DO STEPS OF CODE IN THE ORDER SPECIFIED 

first step -> second step -> third step


```python
number = int(input("Enter a number: "))

result = number * 2
print("double of " + str(number) + " is " + str(result))

```


1. Create a variable based on user input <br>
2. Multiply variable by two<br>
3. Print out both variables at the end<br>



## SELECTION 

### <mark> Choose TWO OR MORE OUTCOMES based on a DECISION or CONDITION 



```python
number = 6
if number % 2 == 0:
    print("Even")
else:
    print("Odd")

```

1. Set number to 5 <br>
2. If number is divisible by 2 with no remainder, print "Even" <br>
3. Otherwise, print "Odd" <br>


# ITERATION 

## <mark> REPEAT STEPS BASED ON A DECISION or STOP when a condition is met 

first step -> 
second step -> 
if step 2: true -> first step 
if step 2: false -> third step 
-> fourth step 


```python

fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)


```

1. Create a list called fruits <br>
2. For each fruit in the list, print the fruit


# ACTIVITY 1: Robot Pseudocode 

[Link to Robot Question 2](https://assets.learnosity.com/organisations/537/VR165972.g03.png)

Write the pseudocode to move the robot onto the gray square. 

Available Code: <br>
Move forward <br>
Turn Left <br>
Turn Right <br>





PseudoCode here: Move 4 left Move 3 down Move 4 Left


```python
# Math Operations:

print("Addition") #addition
result = 5 + 3
print(result)  # 8

print("\nSubtraction") #subtraction
result = 10 - 4
print(result)  # 6

print("\nMultiplication") #multiplication
result = 6 * 7
print(result)  # 42

print("\nFloat Division") #float division (float = numbers with decimal values)
result = 20 / 4
print(result)  # 5.0

print("\nInteger Division (floor division)") #floor division
result = 20 // 4
print(result)  # 5

print("\nModulus (remainder)") #remainder
result = 10 % 3
print(result)  # 1
```

## Fibonacci 


```python
def fibonacci(n): #fibonacci sequence 
    fib_series = [0, 1]  

    while len(fib_series) < n:
        next_number = fib_series[-1] + fib_series[-2]  
        fib_series.append(next_number)  

    return fib_series

n = 10  
result = fibonacci(n)
print(result)  # [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]

# initial length of list is 2 
# while length of list is less than amount of numbers we want in our final sequence
# add the last two numbers of the list 
# add this value to the end of the list 
# repeat until length of list reaches n

```

## Mini Lesson: If, Else Statements


```python
num =0

if num > 0:
    print(str(num) + " is positive.")
elif num < 0:
    print(str(num) + " is negative.")
else:
    print(str(num) + " is zero.")

```

## Mini Lesson 2: For, While Loops


```python
names = ["Alice", "Bob", "Charlie", "David", "Eve"]
for name in names:
    print(name)


num = 1
while num <= 5:
    print(num)
    num += 1

```

## Mini Lesson 3: Defining Function 


```python

def calculate_square(number):
    square = number * number
    return square #ends function 

result = calculate_square(5)
print(f"The square of 5 is {result}")

```

## Mini Lesson 4: Input


```python
variable1 = input("How old are you?")
print("You are " + variable1 + " years old")
```

# ACTIVITY 2: CALCULATOR 
1. Create calculator function <br>
2. Allow user to Choose 2 numbers and an operator <br>
3. Perform specified operation based on input <br>
4. Return result of calculation <br>



```python
##YOUR WORK HERE 
##Hint: Use if else statements, defining functions, input

# Function to add two numbers
def add(x, y):
    return x + y

# Function to subtract two numbers
def subtract(x, y):
    return x - y

# Function to multiply two numbers
def multiply(x, y):
    return x * y

# Function to divide two numbers
def divide(x, y):
    if y == 0:
        return "Cannot divide by zero"
    return x / y

# Main calculator loop
while True:
    # Display menu
    print("Options:")
    print("Enter 'add' for addition")
    print("Enter 'subtract' for subtraction")
    print("Enter 'multiply' for multiplication")
    print("Enter 'divide' for division")
    print("Enter 'quit' to end the program")

    # Take user input
    user_choice = input(": ")

    # Check if the user wants to quit
    if user_choice == "quit":
        break

    # Check if the user's choice is a valid operation
    if user_choice in ("add", "subtract", "multiply", "divide"):
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))

        if user_choice == "add":
            print("Result:", add(num1, num2))
        elif user_choice == "subtract":
            print("Result:", subtract(num1, num2))
        elif user_choice == "multiply":
            print("Result:", multiply(num1, num2))
        elif user_choice == "divide":
            print("Result:", divide(num1, num2))
    else:
        print("Invalid input. Please enter a valid operation.")

```


```python
# String Operations and Concatenation:

print("\nString Concatenation") #add together strings
str1 = "Hello"
str2 = "World"
result = str1 + " " + str2
print(result)  # "Hello World"

print("\nString Length") #length of string
text = "This is a sample text."
length = len(text)
print(length)  # 22

print("\nString Indexing and Slicing") #string slicing 
text = "Python"
first_char = text[0]
substring = text[2:5]
print(first_char)  # 'P'
print(substring)  # 'tho'


print("\nString Repetition (Repeating Strings)")
text = "Repeat "
result = text * 3
print(result)  # "Repeat Repeat Repeat "

# Palindrome Check Algorithm:

print("\nPalindrome Check Algorithm")

def is_palindrome(text):
    text = text.replace(" ", "").lower()
    return text == text[::-1] ## == will return boolean 

result1 = is_palindrome("racecar")
result2 = is_palindrome("Hello, World!")

print(result1)  # True
print(result2)  # False
```

# ACTIVITY 3: COUNTING VOWELS
1. Create a function that takes a word as an input <br>
2. Use a for loop to iterate through each character of a word <br>
3. Check how many characters in a word contain vowels <br>
4. Return vowel number <br>


```python
##YOUR WORK HERE
```

# <mark> HOMEWORK 
## CREATE TEXT (string) ANALYZER: <br>
### criteria: <br>
1. Accepts input from user <br>
2. Counts total letters, numbers, spaces in a string <br>
3. Counts number of vowels <br>
4. Calculates average word length <br>
5. Correctly displays: total # of characters (including spaces + numbers), total vowels, average word length <br>
### other criteria: <br>
1. ensure that program handles upper and lowercase spelling <br>
2. Test multiple inputs to ensure accuracy 
### Criteria for above 90%: <br>
1. Add a unique program, function, or feature not specified by criterias



```python
def count_characters(text):
    # Initialize counters
    total_characters = 0
    total_letters = 0
    total_numbers = 0
    total_spaces = 0
    total_vowels = 0
    word_count = 0
    
    # Define vowels
    vowels = "aeiouAEIOU"
    
    # Character frequencies
    char_frequencies = {}
    for char in text:
        total_characters += 1
        
        if char.isalpha():
            total_letters += 1
            if char in vowels:
                total_vowels += 1
        if char.isdigit():
            total_numbers += 1
        if char.isspace():
            total_spaces += 1
        
        # Update character frequency
        char_frequencies[char] = char_frequencies.get(char, 0) + 1
    
    # Splits the actual user input into words
    words = text.split()
    word_count = len(words)

    # Word frequencies
    word_frequencies = {}
    for word in words:
        word_frequencies[word] = word_frequencies.get(word, 0) + 1

    # Find top 3 most frequent words
    top_3_words = sorted(word_frequencies, key=word_frequencies.get, reverse=True)[:3]

    # Does a basic average calculation to figure out the average length
    if word_count > 0:
        average_word_length = total_characters / word_count
    else:
        average_word_length = 0

    return total_characters, total_vowels, total_spaces, average_word_length, char_frequencies, top_3_words

# Accepts the input the user wishes to give.
user_input = input("Enter a string: ")
total_chars, total_vowels, total_spaces, avg_word_length, char_freqs, top_words = count_characters(user_input)

# Display the results
print("\nInput Text:", user_input)
print("Total # of characters (including spaces + numbers):", total_chars)
print("Total vowels:", total_vowels)
print("Total spaces:", total_spaces)
print("Average word length:", avg_word_length)
print("\nCharacter Frequencies:")
for char, freq in sorted(char_freqs.items(), key=lambda x: x[1], reverse=True):
    print(f"'{char}': {freq}")
print("\nTop 3 Most Frequent Words:", ', '.join(top_words))

```

    
    Input Text: I like dogs more than cats because dogs are better
    Total # of characters (including spaces + numbers): 50
    Total vowels: 17
    Total spaces: 9
    Average word length: 5.0
    
    Character Frequencies:
    ' ': 9
    'e': 7
    's': 4
    't': 4
    'a': 4
    'o': 3
    'r': 3
    'd': 2
    'g': 2
    'c': 2
    'b': 2
    'I': 1
    'l': 1
    'i': 1
    'k': 1
    'm': 1
    'h': 1
    'n': 1
    'u': 1
    
    Top 3 Most Frequent Words: dogs, I, like

