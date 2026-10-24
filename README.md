#1. Student Marks Analyzer

students = {
    "Rahul": 78,
    "Aman": 92,
    "Priya": 85,
    "Rohit": 67,
    "Neha": 95
}

average = sum(students.values()) / len(students)

print("Average:", average)
print("Highest:", max(students, key=students.get))
print("Lowest:", min(students, key=students.get))

for name, marks in students.items():
    if marks >= 90:
        grade = "A"
    elif marks >= 75:
        grade = "B"
    elif marks >= 60:
        grade = "C"
    elif marks >= 40:
        grade = "D"
    else:
        grade = "F"

    result = "Pass" if marks >= 40 else "Fail"
    print(name, marks, grade, result)

top_3 = sorted(students.items(), key=lambda x: x[1], reverse=True)[:3]

print("Top 3:", top_3)
____________________________________________________________________________________________________________________________________________________________________________

#2. Expense Tracker
expenses = {
    "Food": 1200,
    "Travel": 800,
    "Shopping": 2500,
    "Food": 1500,
    "Mobile": 500
}

total = sum(expenses.values())

print("Total Expense:", total)

highest = max(expenses.values())
print("Highest Expense:", highest)

for category, amount in expenses.items():
    print(category, amount)
____________________________________________________________________________________________________________________________________________________________________________

3. #Number Guessing Game
4. import random

number = random.randint(1, 100)

while True:
    guess = int(input("Guess the number: "))

    if guess > number:
        print("Too high")
    elif guess < number:
        print("Too low")
    else:
        print("Correct!")
        break
____________________________________________________________________________________________________________________________________________________________________________

4. #ATM Simulator
balance = 10000

while True:

    print("\n1. Check Balance")
    print("2. Deposit")
    print("3. Withdraw")
    print("4. Exit")

    choice = int(input("Enter choice: "))

    if choice == 1:
        print("Balance:", balance)

    elif choice == 2:
        amount = int(input("Enter deposit amount: "))
        balance = balance + amount
        print("New Balance:", balance)

    elif choice == 3:
        amount = int(input("Enter withdrawal amount: "))

        if amount <= balance:
            balance = balance - amount
            print("New Balance:", balance)
        else:
            print("Insufficient Balance")

    elif choice == 4:
        print("Thank you")
        break

    else:
        print("Invalid choice")
____________________________________________________________________________________________________________________________________________________________________________

5. #Contact Book
contacts = {}

while True:

    print("\n1. Add Contact")
    print("2. Search Contact")
    print("3. Show Contacts")
    print("4. Delete Contact")
    print("5. Exit")

    choice = int(input("Enter choice: "))

    if choice == 1:
        name = input("Enter name: ")
        phone = input("Enter phone: ")

        contacts[name] = phone

        print("Contact Added")

    elif choice == 2:
        name = input("Enter name: ")

        if name in contacts:
            print("Phone:", contacts[name])
        else:
            print("Contact not found")

    elif choice == 3:
        for name, phone in contacts.items():
            print(name, phone)

    elif choice == 4:
        name = input("Enter name: ")

        if name in contacts:
            del contacts[name]
            print("Contact Deleted")
        else:
            print("Contact not found")

    elif choice == 5:
        break

    else:
        print("Invalid choice")
____________________________________________________________________________________________________________________________________________________________________________

6. #Shopping Cart
products = {
    "Laptop": 50000,
    "Mouse": 500,
    "Keyboard": 1200,
    "Headphones": 2000
}

cart = {}

while True:

    print("\nProducts:")
    for product, price in products.items():
        print(product, price)

    name = input("Enter product or exit: ")

    if name == "exit":
        break

    if name in products:

        quantity = int(input("Enter quantity: "))

        cart[name] = quantity

    else:
        print("Product not found")

total = 0

for product, quantity in cart.items():

    price = products[product]
    amount = price * quantity

    total = total + amount

    print(product, quantity, amount)

print("Total Bill:", total)

if total >= 50000:
    discount = total * 0.10
else:
    discount = 0

final_amount = total - discount

print("Discount:", discount)
print("Final Amount:", final_amount)
____________________________________________________________________________________________________________________________________________________________________________

7. #Quiz Application
questions = [
    ["Capital of India?", "Delhi"],
    ["2 + 2?", "4"],
    ["Python creator?", "Guido"],
    ["5 * 5?", "25"],
    ["Largest planet?", "Jupiter"]
]

score = 0

for question, answer in questions:

    user_answer = input(question + " ")

    if user_answer.lower() == answer.lower():
        print("Correct")
        score = score + 1
    else:
        print("Wrong")

print("Score:", score)
print("Percentage:", score / len(questions) * 100)
____________________________________________________________________________________________________________________________________________________________________________

8. #Bank Transaction Analyzer
transactions = [
    5000,
    -1200,
    -500,
    3000,
    -800,
    2000
]

deposits = []
withdrawals = []

for amount in transactions:

    if amount > 0:
        deposits.append(amount)
    else:
        withdrawals.append(abs(amount))

print("Total Deposits:", sum(deposits))
print("Total Withdrawals:", sum(withdrawals))

balance = sum(transactions)

print("Current Balance:", balance)
print("Highest Transaction:", max(transactions))
print("Lowest Transaction:", min(transactions))
print("Number of Withdrawals:", len(withdrawals))
____________________________________________________________________________________________________________________________________________________________________________

import numpy as np
sugar_levels = np.array([85, 140, 165, 95, 210, 130, 180, 75, 155, 110])
print("Avrage Blood Sugar:",sugar_levels.mean())
print("Max Boold Sugar:",sugar_levels.max())
print("Max Boold Sugar:",sugar_levels.min())
print(sugar_levels[np.where(sugar_levels >= 140)])
print(sugar_levels[np.where(sugar_levels >=100)and(sugar_levels<=160)])
print(len(sugar_levels[np.where(sugar_levels >=140)]))
print(sugar_levels%10)
______________________________________________________________________________________________
import pandas as pd
data = {
    "Name": ["Aman", "Riya", "Rohit", "Neha", "Karan", "Priya"],
    "Age": [65, 22, 72, 45, 60, 30],
    "Department": ["Cardiology", "Neurology", "Cardiology", "Ortho", "Neurology", "Ortho"],
    "Billing": [50000, 25000, 75000, None, 40000, 30000],
    "Status": ["Admitted", "Discharged", "Admitted", "Admitted", "Discharged", "Admitted"]
}
df = pd.DataFrame(data)
print(df.shape)
df["Billing"]=df["Billing"].where(df["Billing"].notna(),df["Billing"].mean())
print(df.loc[df["Age"]>=50,"Name"])
print(df.groupby("Department")["Billing"].mean())
print((df["Status"]=="Admitted").sum())
print(df.sort_values(by="Age",ascending=False))
______________________________________________________________________________________________
from common_imports import *
data = {
    "Department": ["Cardiology", "Neurology", "Cardiology", "Ortho", "Neurology", "Ortho"],
    "Age": [65, 22, 72, 45, 60, 30],
    "Billing": [50000, 25000, 75000, 35000, 40000, 30000]
}
df = pd.DataFrame(data)
plt.figure(figsize=(8,5))
plt.plot(df.groupby("Department")["Billing"].mean())
plt.show()
plt.hist(df["Age"],bins=15)
plt.show()
plt.scatter(df["Age"],df["Billing"])
plt.show()
data = pd.get_dummies(df[["Age","Billing","Department"]], columns=["Department"],dtype=int)
sns.heatmap(data.corr(), annot=True, cmap="coolwarm")
plt.show()
_____________________________________________________________________________________________________________________________________________________________________________________________________________________________
