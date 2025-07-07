# engineering-calc.
 the calculators basically used by eng. students for calculating log, trigonometry,etc using python (just gave a try)
import math

def menu():
    print("\n===== Engineering Calculator =====") # creating calculator
    print("1. Basic Arithmetic")
    print("2. Trigonometric Functions")
    print("3. Logarithmic Functions")
    print("4. Power and Roots")
    print("5. Unit Conversion")
    print("6. Exit")

def arithmetic():
    a = float(input("Enter first number: "))# user input
    op = input("Operator (+, -, *, /): ")
    b = float(input("Enter second number: "))# user input
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
            print("Error: Cannot divide by zero")
    else:
        print("Invalid operator!")

def trig():
    angle = float(input("Enter angle in degrees: "))# user input
    rad = math.radians(angle)
    print(f"sin({angle}) = {math.sin(rad):.4f}")
    print(f"cos({angle}) = {math.cos(rad):.4f}")
    print(f"tan({angle}) = {math.tan(rad):.4f}")

def logarithm():
    x = float(input("Enter positive number: "))# user input
    if x > 0:
        print(f"log10({x}) = {math.log10(x):.4f}")
        print(f"ln({x}) = {math.log(x):.4f}")
    else:
        print("Error: Input must be positive")

def power_root():
    base = float(input("Enter base: "))# user input
    exp = float(input("Enter exponent: "))# user input
    print(f"{base} ^ {exp} = {math.pow(base, exp):.4f}")
    if base >= 0:
        print(f"√{base} = {math.sqrt(base):.4f}")
    else:
        print("Square root of negative number is complex")

def convert_units():
    print("\n--- Unit Conversion ---")
    print("1. Meters to Centimeters")
    print("2. Celsius to Fahrenheit")
    print("3. Kilometers to Miles")
    choice = input("Choose option: ")
    if choice == '1':
        meters = float(input("Enter meters: "))# user input
        print(f"{meters} m = {meters * 100} cm")
    elif choice == '2':
        celsius = float(input("Enter temperature in Celsius: "))# user input
        print(f"{celsius} °C = {(celsius * 9/5) + 32} °F")
    elif choice == '3':
        km = float(input("Enter kilometers: "))# user input
        print(f"{km} km = {km * 0.621371} miles")
    else:
        print("Invalid choice!")

# Main loop
while True:
    menu()
    option = input("Choose option (1-6): ")
    if option == '1':
        arithmetic()
    elif option == '2':
        trig()
    elif option == '3':
        logarithm()
    elif option == '4':
        power_root()
    elif option == '5':
        convert_units()
    elif option == '6':
        print("Exiting... Goodbye!")
        break
    else:
        print("Invalid option. Try again.")
