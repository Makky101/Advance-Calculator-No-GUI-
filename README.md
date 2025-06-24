# Advance-Calculator-No-GUI-
#BACKEND ADVANCE CALCULATOR! NO GUI

import math

def Operation(Opr, Num1, Num2):
    try:
        if Opr == '+':
            return Num1 + Num2
        elif Opr == '-':
            return Num1 - Num2
        elif Opr == '*':
            return Num1 * Num2
        elif Opr == '/':
            if Num2 == 0:
                return "Error: Cannot divide by zero."
            return Num1 // Num2
        elif Opr == '%':
            return Num1 % Num2
        elif Opr == '^':
            return Num1 ** Num2
        elif Opr == 'sqrt':
            if Num1 < 0:
                return "Error: Negative numbers cannot have real square roots."
            return math.sqrt(Num1)
        else:
            return "Error: Unsupported operation."
    except Exception as a:
        return f"Error: {a}"

def Calculator():
    print("=====Advanced Calculator(No GUI)=====")
    print()
    print("Operations: +, -, *, /, %, ^, sqrt")
    print()
    print("Press 'e' to Exit.")

    while True:
        Opr = input("Enter operation: ").strip().lower()

        if Opr == 'e':
            print("Goodbye!")
            break

        if Opr == 'sqrt':
            try:
                Num1 = float(input("Enter number: "))
                result = Operation(Opr, Num1)
                print("Result:", result)
            except ValueError:
                print("Error: Invalid number.")
        elif Opr in ['+', '-', '*', '/', '%', '^']:
            try:
                Num1 = float(input("Enter first number: "))
                Num2 = float(input("Enter second number: "))
                result = Operation(Opr, Num1, Num2)
                print("Result:", result)
            except ValueError:
                print("Error: Please enter valid numbers.")
        else:
            print("Invalid operator. Please try again.")

        print()


Calculator()
