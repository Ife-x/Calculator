# Calculator

#Calculator
logo = ("""
 _____________________
|  _________________  |
| | Pythonista   0. | |  .----------------.  .----------------.  .----------------.  .----------------. 
| |_________________| | | .--------------. || .--------------. || .--------------. || .--------------. |
|  ___ ___ ___   ___  | | |     ______   | || |      __      | || |   _____      | || |     ______   | |
| | 7 | 8 | 9 | | + | | | |   .' ___  |  | || |     /  \     | || |  |_   _|     | || |   .' ___  |  | |
| |___|___|___| |___| | | |  / .'   \_|  | || |    / /\ \    | || |    | |       | || |  / .'   \_|  | |
| | 4 | 5 | 6 | | - | | | |  | |         | || |   / ____ \   | || |    | |   _   | || |  | |         | |
| |___|___|___| |___| | | |  \ `.___.'\  | || | _/ /    \ \_ | || |   _| |__/ |  | || |  \ `.___.'\  | |
| | 1 | 2 | 3 | | x | | | |   `._____.'  | || ||____|  |____|| || |  |________|  | || |   `._____.'  | |
| |___|___|___| |___| | | |              | || |              | || |              | || |              | |
| | . | 0 | = | | / | | | '--------------' || '--------------' || '--------------' || '--------------' |
| |___|___|___| |___| |  '----------------'  '----------------'  '----------------'  '----------------' 
|_____________________|
""")

def add(n1,n2):
  return n1 + n2

def subtract(n1,n2):
  return n1 - n2

def multiply(n1, n2):
  return n1 * n2


def divide(n1,n2):
  return n1 / n2

statistics = {
  '+' :add,
  '-': subtract,
  '*' : multiply,
  '/': divide,
}

def calculator ():
  print(logo)
  num1 = float(input('What is the first number?\n'))

  for keys in statistics:
    print(keys)
  can_continue = True

  while can_continue:
    operations = input("pick a key from the options above?\n")
    num2 = float(input('What is the second number?\n'))
    operation_function= statistics[operations]
    answer = operation_function(num1,num2)
    print(f"{num1} {operations} {num2} = {answer}")
    if input (f"Type 'Y' to continue calculation while the {answer}, or type 'n' to start a new calculation.") == 'Y':
      num1 = answer
    else:
      can_continue = False
      calculator()

calculator()
