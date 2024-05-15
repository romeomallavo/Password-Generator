# Password Generator - Python Project

In this project, we will create a password generator using Python. This is a beginner-friendly project that will help you practice your Python skills and potentially learn some new aspects of the language.

## Table of Contents
1. [Introduction](#introduction)
2. [Project Overview](#project-overview)
3. [Setup and Requirements](#setup-and-requirements)
4. [Full Code](#full-code)
5. [Skills and Technologies Learned](#skills-and-technologies-learned)
6. [References](#references)

## Introduction

This repository contains the instructions and code to create a password generator in Python. The project allows you to generate passwords of a specified minimum length and includes options to include numbers and special characters.

## Project Overview

- **Language**: Python
- **IDE**: Visual Studio Code (or any Python environment)
- **Modules**: `random`, `string`

## Setup and Requirements

Make sure you have Python installed on your system. You can use any version of Python for this project. Set up your Python environment in an IDE like Visual Studio Code.


## Full Code

Here is the full code for the password generator:

```python
import random
import string

def generate_password(min_length, numbers=True, special_characters=True):
    letters = string.ascii_letters
    digits = string.digits
    special = string.punctuation

    characters = letters
    if numbers:
        characters += digits
    if special_characters:
        characters += special

    pwd = ''
    meets_criteria = False
    has_number = False
    has_special = False

    while not meets_criteria or len(pwd) < min_length:
        new_char = random.choice(characters)
        pwd += new_char

        if new_char in digits:
            has_number = True
        elif new_char in special:
            has_special = True

        meets_criteria = True
        if numbers:
            meets_criteria = meets_criteria and has_number
        if special_characters:
            meets_criteria = meets_criteria and has_special

    return pwd

min_length = int(input("Enter the minimum length: "))
has_number = input("Do you want to include numbers? (y/n): ").lower() == 'y'
has_special = input("Do you want to include special characters? (y/n): ").lower() == 'y'

password = generate_password(min_length, has_number, has_special)
print("Generated password:", password)


This project allows you to generate passwords of a specified minimum length
and includes options to include numbers and special characters.

Skills and Technologies Learned:
1. Python Basics: Functions, conditionals, loops, and user input handling.
2. String Manipulation: Using the string module to handle characters, digits, and punctuation.
3. Random Module: Generating random choices from a sequence.
4. User Input: Handling and converting user input.
5. Boolean Logic: Conditional checks and boolean operations.

References:
- Python random module: https://docs.python.org/3/library/random.html
- Python string module: https://docs.python.org/3/library/string.html
- Visual Studio Code: https://code.visualstudio.com/
"""

