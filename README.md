# Expense Tracker Project

expensesList = [] #list of expense in form of dictionary
print("Welcome to Expense Tracker")

while True:

    print("========MENU=======")
    print("1. Add Expense")
    print("2. View all Expenses")
    print("3. Total Expense")
    print("4. Exit")

    choice = int(input("Please Enter your choice: "))

#1. Add Expense

    if(choice == 1):
        date = input(" Enter Date of Expense: ")
        category = input(" Enter category (like: food, travel, shopping, ..): ")
        description = input(" Enter Something else: ")
        amount = float(input(" Enter amount: "))

        expense = {
            "date" : date,
            "category" : category,
            "description" : description,
            "amount" : amount
        }

        expensesList.append(expense)
        print("Your Expense Added Succesfully.")
    
#2. View all Expense

    elif(choice == 2):
        if(len(expensesList) == 0):
            print(" No Expense Added. First add some expense.")
        else:
            print(" Your all Expense ")
            count = 1
            for eachExpense in expensesList:
                print(f"Expense {count} -> {eachExpense["date"]}, {eachExpense["category"]}, {eachExpense["description"]}, {eachExpense["amount"]}")
                count += 1

#3. View total Expense amount

    elif(choice == 3):
        total = 0
        for eachExpense in expensesList:
            total = total + eachExpense["amount"]
        print("\n Total Expense Amount: ", total)

#4. Exit

    elif(choice == 4):
        print(" Thank you ")
        break

    else:
        print("INVAILD CHOICE. Try again")



