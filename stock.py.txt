stock_prices = {
    "AAPL": 180,
    "TSLA": 250,
    "GOOGLE": 150,
    "MSFT": 300
}

total = 0

while True:
    stock = input("Enter stock name (or 'done' to finish): ").upper()

    if stock == "DONE":
        break

    if stock in stock_prices:
        quantity = int(input("Enter quantity: "))
        total += stock_prices[stock] * quantity
    else:
        print("Stock not available.")

print("\nTotal Investment Value: $", total)

try:
    with open("portfolio.txt", "w") as file:
        file.write("Total Investment Value: $" + str(total))
    print("Result saved in portfolio.txt")
except PermissionError:
    print("Unable to save the file. Permission denied.")