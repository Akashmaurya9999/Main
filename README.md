# Main
Yah game free fair par bana hai jo ki isse free fair booking bhi hota hai 
class FairApp:
    def __init__(self):
        self.rides = {
            "1": {"name": "Merry-Go-Round", "price": 50},
            "2": {"name": "Roller Coaster", "price": 100},
            "3": {"name": "Ferris Wheel", "price": 80},
        }
        self.balance = 0

    def display_rides(self):
        print("Available Rides:")
        for key, ride in self.rides.items():
            print(f"{key}. {ride['name']} - ₹{ride['price']}")

    def add_balance(self):
        amount = int(input("Enter amount to add: ₹"))
        self.balance += amount
        print(f"Balance: ₹{self.balance}")

    def book_ticket(self):
        self.display_rides()
        choice = input("Enter ride number: ")
        if choice in self.rides:
            ride = self.rides[choice]
            if self.balance >= ride["price"]:
                self.balance -= ride["price"]
                print(f"Ticket booked for {ride['name']}. Remaining balance: ₹{self.balance}")
            else:
                print("Insufficient balance!")
        else:
            print("Invalid choice!")

    def run(self):
        while True:
            print("\nFree Fair App")
            print("1. Add Balance")
            print("2. Book Ticket")
            print("3. Check Balance")
            print("4. Exit")
            choice = input("Enter choice: ")
            if choice == "1":
                self.add_balance()
            elif choice == "2":
                self.book_ticket()
            elif choice == "3":
                print(f"Balance: ₹{self.balance}")
            elif choice == "4":
                break
            else:
                print("Invalid choice!")

if __name__ == "__main__":
    app = FairApp()
    app.run()
