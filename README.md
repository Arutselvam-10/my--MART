import java.util.*;

class Product {
    private int id;
    private String name;
    private double price;

    public Product(int id, String name, double price) {
        this.id = id;
        this.name = name;
        this.price = price;
    }

    public int getId() {
        return id;
    }
    public String getName() {
        return name;
    }
    public double getPrice() {
        return price;
    }

    @Override
    public String toString() {
        return id + ". " + name + " - ₹" + price;
    }
}

class CartItem {
    private Product product;
    private int quantity;

    public CartItem(Product product, int quantity) {
        this.product = product;
        this.quantity = quantity;
    }

    public void addQuantity(int qty) {
        this.quantity += qty;
    }

    public double getTotalPrice() {
        return product.getPrice() * quantity;
    }

    public int getQuantity() {
        return quantity;
    }

    public Product getProduct() {
        return product;
    }

    public String toString() {
        return String.format("%-20s x%-2d ₹%-6.2f", product.getName(), quantity, getTotalPrice());
    }
}

class Cart {
    private List<CartItem> items = new ArrayList<>();

    public void addItem(Product product, int quantity) {
        for (CartItem item : items) {
            if (item.getProduct().getId() == product.getId()) {
                item.addQuantity(quantity);
                return;
            }
        }
        items.add(new CartItem(product, quantity));
    }

    public void printReceipt() {
        if (items.isEmpty()) {
            System.out.println(" Your cart is empty!");
            return;
        }

        System.out.println("\n=========  TOTAL RECEIPT  =========");
        System.out.printf("%-25s%-10s%-10s\n", "Item", "Qty", "Total");
        System.out.println("----------------------------------------");

        double total = 0;
        for (CartItem item : items) {
            System.out.printf("%-25s%-10d₹%-10.2f\n",
                    item.getProduct().getName(), item.getQuantity(), item.getTotalPrice());
            total += item.getTotalPrice();
        }

        System.out.println("----------------------------------------");
        System.out.printf("Grand Total:                 ₹%.2f\n", total);
        System.out.println("========================================");
        System.out.println("Thank you for shopping with Super-Market!");
    }

    public boolean isEmpty() {
        return items.isEmpty();
    }
}

public class SuperMarket {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        List<Product> products = new ArrayList<>();
        int idCountern = 1;
        products.add(new Product(1, "TOMATO - 1Kg", 40.0));
        products.add(new Product(2, "TOMATO - 500g", 20.0));
        products.add(new Product(3, "TOMATO - 250g", 10.0));

        products.add(new Product(4, "ONION  - 1Kg", 60.0));
        products.add(new Product(5, "ONION  - 500g", 30.0));
        products.add(new Product(6, "ONION  - 250g", 15.0));

        products.add(new Product(7, "MILK  - 1l", 64.0));
        products.add(new Product(8, "MILK  - 500ml", 32.0));
        products.add(new Product(9, "MILK  - 250ml", 16.0));

        products.add(new Product(10, "RICE  - 1kg", 70.0));
        products.add(new Product(11, "RICE  - 500g", 35.0));
        products.add(new Product(12, "RICE - 250g", 17.0));

        products.add(new Product(13, "GREEN CHILI - 1kg", 55.0));
        products.add(new Product(14, "EGG", 7.0));
        products.add(new Product(15, "GHEE", 21.0));
        products.add(new Product(12, "DAIRY MILK", 40.0));
        products.add(new Product(16, "DAIRY MILK", 20.0));
        products.add(new Product(17, "DAIRY MILK", 10.0));

        products.add(new Product(18, "BADAM NUTS", 300.0));
        products.add(new Product(19, "CASHEW NUTS", 270.0));
        products.add(new Product(20, "MUSHROOM", 68.0));
        products.add(new Product(21, "PANEER", 122.0));
        products.add(new Product(22, "NOODLES ", 20.0));
        products.add(new Product(23, "KISAN JAM", 45.0));
        products.add(new Product(24, "MANGO PICKLE", 20.0));
        products.add(new Product(25, "GARLIC PICKLE", 25.0));
        products.add(new Product(26, "LEMON PICKLE", 30.0));

        products.add(new Product(27, "KUR-KURE", 10.0));
        products.add(new Product(28, "BINGO GREEN LAYS", 20.0));
        products.add(new Product(29, "BINGO RED LAYS", 15.0));
        products.add(new Product(30, "DAIRY MILK", 40.0));

        products.add(new Product(31, "CHILLI POWDER ", 10.0));
        products.add(new Product(32, "SAMBAR POWDER", 10.0));
        products.add(new Product(33, "PEPPER POWDER", 25.0));
        products.add(new Product(34, "CHICKEN MASALA", 40.0));
        products.add(new Product(35, "BRIYANI MASALA", 70.0));
        products.add(new Product(36, "MUTTON MASALA", 40.0));
        products.add(new Product(37, "TURMERIC POWDER", 65.0));


        products.add(new Product(40, "MUSTARD SAUCE", 40.0));
        products.add(new Product(41, "KETCHUP", 50.0));
        products.add(new Product(42, "CHILI SAUCE", 60.0));
        products.add(new Product(43, "SOYA SAUCE", 30.0));
        products.add(new Product(44, "VINEGAR", 80.0));
        products.add(new Product(45, "HONEY", 150.0));
        products.add(new Product(46, "SUGAR", 40.0));
        products.add(new Product(47, "TEA POWDER", 40.0));
        products.add(new Product(48, "COFFEE POWDER", 50.0));
        products.add(new Product(49, "BREAD", 60.0));
        products.add(new Product(50, "RUSK", 30.0));
        products.add(new Product(51, "GRAPE WINE", 220.0));

        products.add(new Product(52, "WHITE PAPER NOTE", 30.0));
        products.add(new Product(53, "RULED NOTE", 40.0));
        products.add(new Product(54, "BROWN SHEET", 5.0));
        products.add(new Product(55, "PENCIL", 5.0));
        products.add(new Product(56, "ERASER", 2.0));
        products.add(new Product(57, "SHARPENER", 3.0));
        products.add(new Product(58, "MARKER", 10.0));
        products.add(new Product(59, "PEN", 45.0));
        products.add(new Product(60, "PENCIL BOX", 20.0));
        products.add(new Product(61, "WATER BOTTLE", 50.0));
        products.add(new Product(62, "LUNCH BOX", 100.0));
        products.add(new Product(63, "LUNCH BAG", 300.0));
        products.add(new Product(64, "GRAPH SHEET", 4.0));
        products.add(new Product(65, "CALCULATOR", 200.0));
        products.add(new Product(66, "STAPLER", 50.0));
        products.add(new Product(67, "TAPE", 20.0));
        products.add(new Product(68, "GLUE", 15.0));
        products.add(new Product(69, "SCISSORS", 30.0));
        products.add(new Product(70, "RULER", 10.0));
        products.add(new Product(71, "COMPASS", 15.0));

        products.add(new Product(72, "CAT FOOD", 100.0));
        products.add(new Product(73, "DOG FOOD", 200.0));
        products.add(new Product(74, "FISH FOOD", 80.0));
        products.add(new Product(75, "BIRD FOOD", 60.0));
        products.add(new Product(76, "PET TOY", 150.0));
        products.add(new Product(77, "PET BATHING SOAP", 50.0));
        products.add(new Product(78, "PET SHAMPOO", 100.0));
        products.add(new Product(79, "PET COLLAR", 150.0));
        products.add(new Product(80, "PET LEASH", 200.0));
        products.add(new Product(81, "PET BED", 500.0));
        products.add(new Product(82, "PET CARRIER", 800.0));

        products.add(new Product(83, "TOILET PAPER", 30.0));
        products.add(new Product(84, "HAND SANITIZER", 50.0));
        products.add(new Product(85, "SOAP", 20.0));
        products.add(new Product(86, "SHAMPOO", 150.0));
        products.add(new Product(87, "CONDITIONER", 200.0));
        products.add(new Product(88, "TOOTHPASTE", 40.0));
        products.add(new Product(89, "TOOTHBRUSH", 20.0));
        products.add(new Product(90, "DEODORANT", 100.0));
        products.add(new Product(91, "FACIAL WASH", 80.0));
        products.add(new Product(92, "BODY LOTION", 150.0));
        products.add(new Product(93, "FACE CREAM", 160.0));

        products.add(new Product(94, "2A BATTERY", 12.0));
        products.add(new Product(95, "9V BATTERY", 15.0));
        products.add(new Product(96, "AA BATTERY", 10.0));
        products.add(new Product(97, "AAA BATTERY", 8.0));

        products.add(new Product(98, "100V BULB", 20.0));
        products.add(new Product(99, "L E D BULB", 25.0));
        products.add(new Product(100, "FLUORESCENT TUBE", 30.0));
        products.add(new Product(101, "EXTENSION CORD", 100.0));

        System.out.println(" Welcome to Super-Market!");
        System.out.println("Available Products:");
        for (Product p : products) {
            System.out.println("  " + p);
        }

        Cart cart = new Cart();

        while (true) {
            try {
                System.out.print("\nEnter Product ID (0 to checkout): ");
                int id = scanner.nextInt();

                if (id == 0) break;

                Product selected = null;
                for (Product p : products) {
                    if (p.getId() == id) {
                        selected = p;
                        break;
                    }
                }

                if (selected == null) {
                    System.out.println(" Invalid Product ID.");
                    continue;
                }

                System.out.print("Enter quantity: ");
                int qty = scanner.nextInt();

                if (qty <= 0) {
                    System.out.println(" Invalid quantity.");
                    continue;
                }

                cart.addItem(selected, qty);
                System.out.println("Added: " + selected.getName() + " x" + qty);

            } catch (InputMismatchException e) {
                System.out.println(" Please enter a valid number.");
                scanner.next();
            }
        }

        
        cart.printReceipt();
    }
}
