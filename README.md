import random
import string

def generate_password(length=12):
    # Define character sets
    lower = string.ascii_lowercase
    upper = string.ascii_uppercase
    digits = string.digits
    special = string.punctuation

    # Ensure the password has at least one of each type of character
    all_characters = lower + upper + digits + special
    password = [
        random.choice(lower),
        random.choice(upper),
        random.choice(digits),
        random.choice(special)
    ]

    # Fill the rest of the password length with random choices from all character sets
    password += random.choices(all_characters, k=length-4)

    # Shuffle the resulting password list to ensure randomness
    random.shuffle(password)

    # Convert the list to a string and return
    return ''.join(password)

# Example usage
print(generate_password(12))

