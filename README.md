# Designing-Automata-for-Real-time-applications

import re

# 1. Password Verification
def verify_password(password):
    if (
        len(password) >= 8
        and re.search(r"[A-Z]", password)
        and re.search(r"[a-z]", password)
        and re.search(r"[0-9]", password)
        and re.search(r"[^A-Za-z0-9]", password)
    ):
        return "Valid Password"
    return "Invalid Password"


# 2. Email Format Validator
def validate_email(email):
    pattern = r"^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$"

    if re.fullmatch(pattern, email):
        return "Valid Email"
    return "Invalid Email"


# 3. ATM PIN Verification
def verify_pin(pin):
    if re.fullmatch(r"[0-9]{4}", pin):
        return "Valid PIN Format"
    return "Invalid PIN Format"


# Main Menu
while True:
    print("\n===== AUTOMATA APPLICATIONS =====")
    print("1. Password Verification")
    print("2. Email Validation")
    print("3. ATM PIN Verification")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        password = input("Enter password: ")
        print(verify_password(password))

    elif choice == "2":
        email = input("Enter email: ")
        print(validate_email(email))

    elif choice == "3":
        pin = input("Enter 4-digit PIN: ")
        print(verify_pin(pin))

    elif choice == "4":
        print("Exiting application...")
        break

    else:
        print("Invalid choice!")
