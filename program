class CoffeeMachine:
    def __init__(self):
        self.resources = {
            "water": 400,
            "milk": 540,
            "coffee beans": 120,
            "disposable cups": 9,
            "money": 550
        }

    def remaining(self):
        print(f"""\nThe coffee machine has:
{self.resources["water"]} ml of water
{self.resources["milk"]} ml of milk
{self.resources["coffee beans"]} g of coffee beans
{self.resources["disposable cups"]} disposable cups
${self.resources["money"]} of money""")

    def take(self):
        print(f'I gave you ${self.resources["money"]}')
        self.resources["money"] = 0

    def fill(self):
        self.resources["water"] += int(input("Write how many ml of water you want to add:\n"))
        self.resources["milk"] += int(input("Write how many ml of milk you want to add:\n"))
        self.resources["coffee beans"] += int(input("Write how many grams of coffee beans you want to add:\n"))
        self.resources["disposable cups"] += int(input("Write how many disposable cups you want to add:\n"))

    def buy(self):
        costs = {
            "espresso": {
                "water": 250,
                "coffee beans": 16,
                "money": 4
            },
            "latte": {
                "water": 350,
                "milk": 75,
                "coffee beans": 20,
                "money": 7
            },
            "cappuccino": {
                "water": 200,
                "milk": 100,
                "coffee beans": 12,
                "money": 6
            }
        }
        key = {
            "1": "espresso",
            "2": "latte",
            "3": "cappuccino"
        }
        order = input("What do you want to buy? 1 - espresso, 2 - latte, 3 - cappuccino, back - to main menu:\n")
        if order == "back":
            return
        drink = key[order]
        values = costs[drink]
        if values["water"] <= self.resources["water"]:
            self.resources["water"] -= values["water"]
        else:
            print("Sorry, not enough water!")
            return
        if values["coffee beans"] <= self.resources["coffee beans"]:
            self.resources["coffee beans"] -= values["coffee beans"]
        else:
            print("Sorry, not enough coffee beans!")
            return
        if self.resources["disposable cups"] != 0:
            self.resources["disposable cups"] -= 1
        else:
            print("Sorry, not enough disposable cups!")
            return
        self.resources["money"] += values["money"]
        if order != "1":
            if values["milk"] <= self.resources["milk"]:
                self.resources["milk"] -= values["milk"]
            else:
                print("Sorry, not enough milk!")
                return
        print("I have enough resources, making you a coffee!")


def main():
    coffee_machine = CoffeeMachine()
    while True:
        action = input("\nWrite action (buy, fill, take, remaining, exit):\n").lower()
        if action == "buy":
            coffee_machine.buy()
        elif action == "fill":
            coffee_machine.fill()
        elif action == "take":
            coffee_machine.take()
        elif action == "remaining":
            coffee_machine.remaining()
        else:
            break


if __name__ == "__main__":
    main()
