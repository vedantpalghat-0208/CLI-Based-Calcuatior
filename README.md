def add(*args):
    return sum(args)


def sub(*args):
    if not args:
        return "No numbers provided"
    result = args[0]
    for i in args[1:]:
        result -= i
    return result


def mul(*args):
    if not args:
        return "No numbers provided"
    result = args[0]
    for i in args[1:]:
        result *= i
    return result


def divide(*args):
    if not args:
        return "No numbers provided"
    result = float(args[0])
    for i in args[1:]:
        if i == 0:
            return "Error: Can't divide by zero"
        result /= i
    return result


def mod(*args):
    if not args:
        return "No numbers provided"
    result = args[0]
    for i in args[1:]:
        if i == 0:
            return "Error: Can't modulo by zero"
        result %= i
    return result

def power(*args):
    if not args:
        return "No numbers provided"
    result = args[0]
    for i in args[1:]:
        result **= i
    return result

def sq(*args):
    if len(args) != 1:
        return "Error: Only one number allowed"
    return args[0] ** 0.5

print("| CLI BASED CALCULATOR |")
print("!! ONLY ONE METHOD CAN BE APPLIED AT A TIME !!")

print("""
1) Addition
2) Subtraction
3) Multiplication
4) Division
5) Modulo
6) Power
7) Square Root
""")

met = int(input("Choose method: "))

n = int(input("Enter number of values: "))

numbers = []

if met == 7 and n != 1:
    print("Square root needs exactly 1 number")
    exit()

for i in range(1, n + 1):
    num = float(input(f"Enter Number {i}: "))
    numbers.append(num)


match met:
    case 1:
        print("Result:", add(*numbers))
    case 2:
        print("Result:", sub(*numbers))
    case 3:
        print("Result:", mul(*numbers))
    case 4:
        print("Result:", divide(*numbers))
    case 5:
        print("Result:", mod(*numbers))
    case 6:
        print("Result:", power(*numbers))
    case 7:
        print("Result:", sq(*numbers))
    case _:
        print("Invalid choice")
