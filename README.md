🛒 Super-Market Billing System (Java OOP Project)
A simple console-based billing system for a supermarket, built using Java and Object-Oriented Programming (OOP) concepts. The program allows customers to select products, enter quantities, and generate a receipt with a total bill.

✅ Features
List of 100+ pre-defined products across different categories

Search and select products by ID

Input desired quantity

Cart system to manage selected items

Automatically combine duplicate items

Clear and formatted receipt generation

Uses core OOP principles: Classes, Encapsulation, Lists

Handles input validation and exceptions
--------------------------------------------------------------------------------------------------------------------------------------------
🧱 Classes Used:

Class	Responsibility

Product	Represents a single product (ID, name, price)

CartItem	Represents an item in the cart (Product + Quantity)

Cart	Manages list of items, adds items, prints receipt

SuperMarket	Main class – displays products, accepts input, processes logic

-----------------------------------------------------------------------------------------------------------------------------------------------
📦 Product Categories
Vegetables (Tomato, Onion, etc.)

Dairy (Milk, Paneer, Ghee)

Groceries (Rice, Nuts, Pickles, Masalas)

Snacks (Chips, Chocolates)

Stationery (Pens, Notes, Calculator)

Pet Supplies (Food, Toys, Grooming)

Toiletries (Soap, Shampoo, Toothpaste)

Electronics (Batteries, Bulbs, Cords)

-----------------------------------------------------------------------------------------------------------------------------------------------
🖥️ How to Run
*Clone or download the repository.

*Open the project in any Java IDE (e.g., IntelliJ, Eclipse) or a terminal.

Compile the program:
javac SuperMarket.java

Run the program:
java SuperMarket


🧪 Sample Output
markdown
Welcome to Super-Market!
Available Products:
1. TOMATO - 1Kg - ₹40.0
...
Enter Product ID (0 to checkout): 1
Enter quantity: 2
Added: TOMATO - 1Kg x2

=========  TOTAL RECEIPT  =========
Item                     Qty       Total     
----------------------------------------
TOMATO - 1Kg             2         ₹80.00    
----------------------------------------
Grand Total:                 ₹80.00
========================================
Thank you for shopping with Super-Market!
------------------------------------------------------------------------------------------------------------------------------------------------

⚙️ Requirements
Java 8 or higher

Terminal or IDE that supports Java

📚 Concepts Demonstrated
Java Collections (ArrayList)

Object-Oriented Programming (Encapsulation, Composition)

Scanner for user input

try-catch for input validation

toString() method overriding

Clean console formatting

✍️made by
. ARUT SELVAM K


