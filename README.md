from colorama import Fore, Style, init
init(autoreset=True)

def logo():
    print(Fore.CYAN + """
   _____________________
   |  _________________  |
   | | Python Calc     | |
   | |_________________| |
   |  ___ ___ ___   ___  |
   | | 7 | 8 | 9 | | + | |
   | |___|___|___| |___| |
   | | 4 | 5 | 6 | | - | |
   | |___|___|___| |___| |
   | | 1 | 2 | 3 | | * | |
   | |___|___|___| |___| |
   | | . | 0 | = | | / | |
   | |___|___|___| |___| |
   |_____________________|
    """ + Style.RESET_ALL)

def add(n1,n2): return n1+n2
def sub(n1,n2): return n1-n2
def mul(n1,n2): return n1*n2
def div(n1,n2): return n1/n2

operations = {"+": add, "-": sub, "*": mul, "/": div}

def calculator():
    logo()
    num1 = float(input(Fore.YELLOW + "Enter the first number: " + Style.RESET_ALL))
    should_accumulate = True

    while should_accumulate:
        print(Fore.GREEN + "Available operations:" + Style.RESET_ALL)
        for symbol in operations: print(symbol)

        operation_symbol = input(Fore.CYAN + "Pick an operation: " + Style.RESET_ALL)
        num2 = float(input(Fore.YELLOW + "Enter the next number: " + Style.RESET_ALL))

        answer = operations[operation_symbol](num1, num2)
        print(Fore.MAGENTA + f"{num1} {operation_symbol} {num2} = {answer}" + Style.RESET_ALL)

        choice = input(Fore.BLUE + f"Type 'y' to continue with {answer}, 'n' to restart, or 'exit' to quit: " + Style.RESET_ALL).lower()

        if choice == "y":
            num1 = answer
        elif choice == "n":
            print("\n" * 20)
            calculator()
            return
        elif choice == "exit":
            should_accumulate = False
            print(Fore.RED + "Goodbye! Thanks for using Python Calc." + Style.RESET_ALL)
        else:
            print(Fore.RED + "Invalid choice, exiting..." + Style.RESET_ALL)
            should_accumulate = False

calculator()
