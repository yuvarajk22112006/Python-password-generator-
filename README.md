'''
Project: Password Generator

Description:
Prompts user for password length.
Uses letters, numbers, and symbols to create a strong password.
Displays the final password.
Includes validation for input.
'''
# code:

import random
import string

def generate_password(length):
    if length < 4:
        return "Password length should be at least 4 characters."

    # Combine all character sets
    characters = string.ascii_letters + string.digits + string.punctuation

    # Use random.choices() to pick characters
    password = ''.join(random.choices(characters, k=length))
    return password

def main():
    print(" Welcome to the Python Password Generator!")

    try:
        length = int(input("Enter desired password length: "))
        password = generate_password(length)
        print("\nGenerated Password:", password)
    except ValueError:
        print("Please enter a valid number.")

# Run the program
main()
