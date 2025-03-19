# ATM-Simulator
# Simple ATM Simulator

# Initial balance
balance = 1000.0

def display_menu():
    print("\nWelcome to the ATM Simulator")
    print("Please choose an option:")
    print("1. Check Balance")
    print("2. Deposit Money")
    print("3. Withdraw Money")
    print("4. Exit")

def check_balance():
    print(f"\nYour current balance is: ${balance:.2f}")

def deposit_money():
    global balance
    amount = float(input("\nEnter the amount to deposit: $"))
    if amount > 0:
        balance += amount
        print(f"${amount:.2f} deposited successfully!")
        check_balance()
    else:
        print("Invalid amount. Please enter a positive number.")

def withdraw_money():
    global balance
    amount = float(input("\nEnter the amount to withdraw: $"))
    if amount > 0:
        if amount <= balance:
            balance -= amount
            print(f"${amount:.2f} withdrawn successfully!")
            check_balance()
        else:
            print("Insufficient funds. Please try a smaller amount.")
    else:
        print("Invalid amount. Please enter a positive number.")

def main():
    while True:
        display_menu()
        choice = input("\nEnter your choice: ")

        if choice == '1':
            check_balance()
        elif choice == '2':
            deposit_money()
        elif choice == '3':
            withdraw_money()
        elif choice == '4':
            print("\nThank you for using the ATM. Goodbye!")
            break
        else:
            print("\nInvalid choice. Please select a valid option.")

# Run the ATM simulator
if __name__ == "_main_":
    main()
