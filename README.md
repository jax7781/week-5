# week-5
Scripts for week 5
def check_equilateral_triangle(side1, side2, side3):
    if side1 == side2 == side3:
        return True
    else:
        return False

side1 = float(input("Enter the length of side 1: "))
side2 = float(input("Enter the length of side 2: "))
side3 = float(input("Enter the length of side 3: "))

if check_equilateral_triangle(side1, side2, side3):
    print("It is an equilateral triangle.")
else:
    print("It is not an equilateral triangle.")

def check_right_triangle(side1, side2, side3):
    sides = [side1, side2, side3]
    sides.sort()  

    if sides[0]**2 + sides[1]**2 == sides[2]**2:
        return True
    else:
        return False

side1 = float(input("Enter the length of side 1: "))
side2 = float(input("Enter the length of side 2: "))
side3 = float(input("Enter the length of side 3: "))

if check_right_triangle(side1, side2, side3):
    print("It is a right triangle.")
else:
    print("It is not a right triangle.")

import math

def guess_number(lower_bound, upper_bound):
    minimum_guesses = math.ceil(math.log2(upper_bound - lower_bound + 1))  # Compute minimum number of guesses
    guesses_taken = 0

    while True:
        guess = (lower_bound + upper_bound) // 2
        print(f"Is your number {guess}?")
        response = input("Enter 'l' if your number is lower, 'h' if higher, or 'c' if correct: ")

        if response == 'c':
            print("Computer guessed the number correctly!")
            break
        elif response == 'l':
            upper_bound = guess - 1
        elif response == 'h':
            lower_bound = guess + 1
        else:
            print("Invalid response. Please enter 'l', 'h', or 'c'.")

        guesses_taken += 1

    print(f"Computer took {guesses_taken} guess(es) to find the number.")
    print(f"The minimum number of guesses needed is {minimum_guesses}.")


print("Think of a number between 1 and 100.")
lower_bound = 1
upper_bound = 100
guess_number(lower_bound, upper_bound)

def calculate_payment_schedule(purchase_price):
    down_payment = purchase_price * 0.1
    balance = purchase_price - down_payment
    monthly_interest_rate = 0.12 / 12
    monthly_payment = (purchase_price - down_payment) * 0.05

    print("Month\tBalance\t\tInterest\tPrincipal\tPayment\t\tRemaining Balance")
    month = 1
    while balance > 0:
        interest = balance * monthly_interest_rate
        principal = monthly_payment - interest
        remaining_balance = balance - principal

        print(f"{month}\t${balance:.2f}\t\t${interest:.2f}\t\t${principal:.2f}\t\t${monthly_payment:.2f}\t\t${remaining_balance:.2f}")

        balance = remaining_balance
        month += 1

purchase_price = float(input("Enter the purchase price: "))

calculate_payment_schedule(purchase_price)
